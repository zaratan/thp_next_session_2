   This section involves the creation of an instance method that returns the `price` of an item and a class method that returns the `average_price` of all the items in the database.   

   Take a good look at the migration file in order to understand how the database was designed, you will eventually have to add attributes and create your own models.   

#### Item model

* original_price  
* has_discount  
* discount_percentage  

#### Specs

1. create a `price` method  

   You want to be able to call a single method `price` on your **item** object that will return a computed price if it has a discount or the original price otherwise.

   ```ruby
   item = Item.first
   item.price
   ```  
   Given the following attributes : (original_price: 15, has_discount: false, discount_percentage: nil)  
   The above code should return **15**

   Given the following attributes : (original_price: 15, has_discount: true, discount_percentage: 20)
   The above code should return **12**

2. create an `average_price` method  

   You want to be able to call a method `average_price` on your **Item** object that will return the average price of all the items in the database.

   ```ruby
   Item.average_price
   ```  

#### Creating the unit tests

1. using factories  

   Use **factories** and **faker** in order to build or create your test objects :   

   ```ruby
    FactoryBot.define do
      factory :item do
        original_price      { Faker::Number.decimal(2) }
        has_discount        { Faker::Boolean.boolean }

        trait :with_discount do
          has_discount { true }
        end

        factory :item_with_discount, traits: %i[with_discount]
      end
    end
   ```  
   This factory supplies two attributes for the `Item` model, it's up to you to add the **discount_percentage**.   

   This factory supplies one trait, it's up to you to add a trait called **without_discount** that will generate an item for which the attribute **has_discount** is set to **false**.   

   Similarly, create a factory named **item_without_discount** that will generate an item with the trait **without_discount**.   

   
2. testing the database  

   Use **shoulda-matchers** in order to test each field of the database. Here is an example of how you can do that :   

   ```ruby
    RSpec.describe Item, type: :model do
      describe 'Model instantiation' do
        subject(:new_item) { described_class.new }

        describe 'Database' do
          it { is_expected.to have_db_column(:id).of_type(:integer) }
          it { is_expected.to have_db_column(:original_price).of_type(:float).with_options(null: false) }
          it { is_expected.to have_db_column(:created_at).of_type(:datetime).with_options(null: false) }
        end

      end
    end
   ```  
   3 of the attributes are tested, it's up to you to **add the 3 missing ones**. Don't forget to check the documentation for a thorough job. Don't worry, it's easier than it looks ;)

3. testing the model  

   This part can be a lot more tricky. It's relatively easy to learn **how** to test an object or a method (learning the syntax and checking the documentation), but it can be an art to design **what** to test. You will soon find out that you can't rely solely on a good coverage in order to consider that your code is fully tested. Your unit tests should be as elementary as possible, meaning that they should only test **one** element.   

   ```ruby
    describe 'Price' do

      context 'when the item has a discount' do
        let(:item) { build(:item_with_discount, original_price: 100.00, discount_percentage: 20) }

        it { expect(item.price).to eq(80.00) }
      end

    end
   ```   

   I'm confident that you will remember to test that things that should work, actually do work. Try not to forget to test that things that shouldn't work, actually don't work ! Also, don't hesitate to use validations if necessary.   
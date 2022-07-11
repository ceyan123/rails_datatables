# source : https://www.youtube.com/watch?v=J3R-kyueb3I&t=2906s  14:34

# github : https://github.com/philsmy/datatables-demo

# rails new datatables_demo

# bundle add jquery-rails

# application.js
//=require jquery

# bundle add jquery-datatables

# rails g scaffold ecomOrder price:float itek_sku purchase_date:datetime platform_order_num sales_channel status customer_name customer_state shipped_at:datetime num_items_shipped:integer payment_method

# rails db:create

# rails db:migrate

# bundle add faker

# seeds.rb
100.times do
  order_type = %w[confirmed shipped delivered].sample
  purchase_date = Faker::Time.backward(days: 30)
  shipped_at = %w[shipped delivered].include?(order_type) ? purchase_date + 3.days : nil

  EcomOrder.create    platform_order_num: "#{Faker::Number.number(digits: 3)}-#{Faker::Number.number(digits: 8)}-#{Faker::Number.number(digits: 8)}",
                      price: Faker::Commerce.price(range: 10..20.99),
                      itek_sku: Faker::Alphanumeric.alphanumeric(number: 10, min_alpha: 3),
                      purchase_date: purchase_date,
                      sales_channel: ['amazon.com', 'ebay.com', 'walmart.com'].sample,
                      status: order_type,
                      customer_name: Faker::Name.name,
                      customer_state: Faker::Address.state,
                      shipped_at: shipped_at,
                      num_items_shipped: [1, 2].sample,
                      payment_method: ['MC', 'V'].sample
end

# rails db:seed

# gem 'bootstrap', '~> 4.1'

# rename application.css to application.scss
@import "bootstrap";

# application.js
//=require popper
//=require bootstrap

# application.html.erb
<div class="container-fluid'>


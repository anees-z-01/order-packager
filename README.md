# Order Packager

The Order Packaging System is a Rails application designed to streamline and optimize the packaging of products within orders. It manages products, packages, and orders, ensuring the most efficient packaging solutions are employed for each order.

### Prerequisites
This project expects the following tools installed on your devise.
- Github
- Ruby [3.0.1]
- Rails [7.0.8]
- Postgres
- npm

## Install
### Clone the repository

```shell
git clone https://github.com/anees-z-01/order-packager.git
cd order-packager
```

### Install dependencies

```shell
bundle i
npm i
```

### Set environment variables
    1. Create .env file
    2. Set DB_USERNAME with your Postgres user
    3. Set DB_PASSWORD with password of that Postgres user

### Initialize the database

```shell
rails db:create db:migrate db:seed
```

### Server

```shell
rails s
```
That's it! You're good to go. Go to [localhost:3000](localhost:3000) and play around!


#### Test Suit
You can run tests locally
```shell
bundle exec rspec
```

#### Assumptions
    1. We need UI for better experience managing(editing) packages
    2. We are not associating packages with order because packages and order can modified. ( So keep data up-to-date)

### Notes
    1. We can improve views (make responsive)
    2. Add more robust and user friendly error display
    3. We can just create the API app for this and use separate front-end/postman to play around

## Package selection as a service

`app/services/package_selector.rb` is the useful design boundary to review alongside its specs. Distinguish the implemented selection rule from a claim of globally optimal packing. Good next cases include empty orders, quantities, unavailable package combinations, and updates made while an order is being reviewed. A sample order and its selected packages would make the UI easier to evaluate; use synthetic inventory.

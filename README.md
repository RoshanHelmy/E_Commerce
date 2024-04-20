# E_Commerce
MAIN CLASS: 
There are 3 product categories [ElectronicProduct , ClothingBrand , BookProduct] each of them has its attributes and it creates instances of these products representing smartphone,T-shirt,and Book. 
This code uses a Scanner to get input from the user. It gets the user to enter his/her customer ID,name,address then it asks the user about how many products he wants and creats Cart object based on the number of products.
The code uses a loop to iterate for the number of products the user wants to add.
Inside the loop, it presents a menu with the three product options (smartphone, T-shirt, book) and asks the user to choose.
Based on the user's choice, it adds the corresponding product object (smartphone, T-shirt, or book) to the user's cart using the addProduct method of the Cart class.
If the user enters an invalid choice, it displays an error message and skips adding a product for that iteration.
After adding products, the code calculates the total price of the cart using the calculatePrice method of the Cart class.
It displays the total price and asks the user whether they want to place the order (1 - Yes, 2 - No).
If the user chooses to place the order (1), the code likely calls a placeOrder method in the Cart class, which might handle tasks like order confirmation or interacting with a payment system.If the user cancels (2), the code displays an "Order canceled" message.

PRODUCT CLASS:
The class provides 3 attributes [productId , name , price] 
Default constructor ,a no-argument constructor. It doesn't take any input parameters and likely initializes the product attributes with default values
Parameterized Constructor (Product(int productId, String name, float price)): This constructor takes three arguments: product ID, name, and price. It assigns these values to the  private attributes of the product object. It also uses Math.abs() on productId and price to ensure they are positive values.
Setter Methods to set each attribute & Getter Methods to return the value of each attribute.

ElectronicProduct CLASS: 
This class inherits all the attributes and method from Product class.
It defines 2 attributes [brand & warrantyPeriod]
It has one constructor that taked 5 arguments and it calls the superclass constructor to initialize the inherited attributes.
Setter Methods to set each attribute & Getter Methods to return the value of each attribute , then it assigns [brand , warrantyPeriod] to their own attributes

ClothingBrand CLASS:
This class inherits all the attributes and method from Product class.
It has one constructor that taked 5 arguments and it calls the superclass constructor to initialize the inherited attributes.
Setter Methods to set each attribute & Getter Methods to return the value of each attribute , then it assigns [size , fabric] to their own attributes.

BookProduct CLASS:
This class inherits all the attributes and method from Product class.
It has one constructor that taked 5 arguments and it calls the superclass constructor to initialize the inherited attributes.
Setter Methods to set each attribute & Getter Methods to return the value of each attribute , then it assigns [authour , publisher] to their own attributes.

CUSTOMER CLASS:
The class provides 3 attributes [customerId , name , address].
The class has one constructor:Customer(int customerId, String name, String address): This constructor takes three arguments to initialize the customer object.
It ensures a positive customerId by using Math.abs().

CART CLASS:
This class has 4 attributes [customerId , nProducts , products , orderId]
The class has one constructor:Cart(int customerId, int nProducts): This constructor takes two arguments to initialize the cart.
It ensures positive values for customerId and nProducts using Math.abs().
It creates a new Product array with a size equal to nProducts to store the products in the cart
The addProduct(Product product) method adds a product to the cart.
It iterates through the products array to find the first null element (empty slot).
If an empty slot is found, it assigns the provided product to that slot.
If the cart is full (all slots occupied), it displays a message indicating no more products can be added.
The addProduct(Product product) method adds a product to the cart.
It iterates through the products array to find the first null element (empty slot).
If an empty slot is found, it assigns the provided product to that slot.
If the cart is full (all slots occupied), it displays a message indicating no more products can be added.
The placeOrder(Customer customer) method creates an order object 
It calculates the total price using calculatePrice().
It creates a new Order object using the generated orderId, customer ID, number of products, product list from the cart, and the total price.
It likely calls an Order method named printOrderInfo(Customer customer) to display the order information for the customer 

ORDER CLASS:
This class has 4 attributes [customerId , totalPrice , products , orderId]
The class has one constructor: Order(int orderId, int customerId, int nProducts, Product[] products, float totalPrice): This constructor takes all the necessary information to initialize an order object.
The printOrderInfo(Customer customer) method displays the details of the order for the customer.
It prints a header message "Here's your order's summary:".
It displays the order ID, customer ID, and a "Products:" section title.
It iterates through the products array.
For each non-null product (product != null), it prints the product name and price using the product's getter methods (getName() and getPrice()).
It displays the total price of the order using printf for better formatting with two decimal places.

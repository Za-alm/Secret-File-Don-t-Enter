class Customer:
    """Represents a customer in the delivery system."""

    def __init__(self, customer_id, name, email, password, address):
        self.customer_id = customer_id
        self.name = name
        self.email = email
        self.password = password
        self.address = address

    # Getters
    def get_customer_id(self):
        return self.customer_id

    def get_name(self):
        return self.name

    def get_email(self):
        return self.email

    def get_password(self):
        return self.password

    def get_address(self):
        return self.address

    # Setters
    def set_name(self, name):
        self.name = name

    def set_email(self, email):
        self.email = email

    def set_password(self, password):
        self.password = password

    def set_address(self, address):
        self.address = address

    # Functional Methods
    def login(self, input_password):
        """Verifies if the input password matches the stored password."""
        if self.password == input_password:
            print("**************************************")

            print("Login successful! Welcome,", self.name)
            return True
        else:
            print("Login failed! Incorrect password.")
            return False

    def place_order(self):
        pass  # To be implemented

    def track_order(self):
        pass  # To be implemented


class Order:
    """Represents an order placed by a customer."""

    def __init__(self, order_id, customer_id, items, status="Pending"):
        self.order_id = order_id
        self.customer_id = customer_id
        self.items = items
        self.status = status

    # Getters
    def get_order_id(self):
        return self.order_id

    def get_customer_id(self):
        return self.customer_id

    def get_status(self):
        return self.status

    def get_items(self):
        return self.items

    # Setters
    def set_order_id(self, order_id):
        self.order_id = order_id

    def set_customer_id(self, customer_id):
        self.customer_id = customer_id

    def set_status(self, status):
        self.status = status

    def set_items(self, items):
        self.items = items

    # Functional Methods
    def verify_availability(self):
        pass  # To be implemented

    def confirm_order(self):
        pass  # To be implemented


class Admin:
    """Represents an administrator managing orders and deliveries."""

    def __init__(self, admin_id, name, email, phone_number):
        self.admin_id = admin_id
        self.name = name
        self.email = email
        self.phone_number = phone_number

    # Getters
    def get_admin_id(self):
        return self.admin_id

    def get_name(self):
        return self.name

    def get_email(self):
        return self.email

    def get_phone_number(self):
        return self.phone_number

    # Setters
    def set_admin_id(self, admin_id):
        self.admin_id = admin_id

    def set_name(self, name):
        self.name = name

    def set_email(self, email):
        self.email = email

    def set_phone_number(self, phone_number):
        self.phone_number = phone_number

    # Functional Methods
    def manage_orders(self):
        pass  # To be implemented

    def assign_delivery(self):
        pass  # To be implemented


class DeliveryStaff:
    """Represents a delivery staff member handling deliveries."""

    def __init__(self, staff_id, name, phone_number, assigned_orders):
        self.staff_id = staff_id
        self.name = name
        self.phone_number = phone_number
        self.assigned_orders = assigned_orders

    # Getters
    def get_staff_id(self):
        return self.staff_id

    def get_name(self):
        return self.name

    def get_phone_number(self):
        return self.phone_number

    def get_assigned_orders(self):
        return self.assigned_orders

    # Setters
    def set_staff_id(self, staff_id):
        self.staff_id = staff_id

    def set_name(self, name):
        self.name = name

    def set_phone_number(self, phone_number):
        self.phone_number = phone_number

    def set_assigned_orders(self, assigned_orders):
        self.assigned_orders = assigned_orders

    # Functional Methods
    def pick_up_package(self):
        pass  # To be implemented

    def update_status(self):
        pass  # To be implemented


class Item:
    """Represents an item available for ordering."""

    def __init__(self, item_id, name, price, stock):
        self.item_id = item_id
        self.name = name
        self.price = price
        self.stock = stock

    # Getters
    def get_item_id(self):
        return self.item_id

    def get_name(self):
        return self.name

    def get_price(self):
        return f"{self.price} AED"

    def get_stock(self):
        return self.stock

    # Setters
    def set_item_id(self, item_id):
        self.item_id = item_id

    def set_name(self, name):
        self.name = name

    def set_price(self, price):
        self.price = price

    def set_stock(self, stock):
        self.stock = stock

    # Functional Methods
    def update_stock(self):
        pass  # To be implemented

    def get_item_details(self):
        pass  # To be implemented


# Example Object Creation
customer1 = Customer(1, "Zayed", "zayed@zu.ac.ae", "Zayed123", "Abu Dhabi, UAE")
order1 = Order(101, customer1.get_customer_id(), ["GeForce RTX 4090", "Mouse"], "Pending")
admin1 = Admin(5001, "Prof. Afshan Parkar", "AfshanParkar@zu.ac.ae", "+971-50-1234567")
staff1 = DeliveryStaff(7001, "Ahmed", "+971-55-9876543", [order1.get_order_id()])
item1 = Item(1001, "GeForce RTX 4090", 3700, 10)


input_password = input("Enter your password: ")
if customer1.login(input_password):  # Login must be successful to show receipt
    # Displaying Object Information
    print("============================================================")
    print("                    Delivery Note                           ")
    print("============================================================")
    print("Thank you for using our delivery service! Please print your delivery receipt and present it upon receiving your items.")


    print("Delivery Receipt:")
    print("__________________________________________________________")
    print(f"Customer: {customer1.get_name()}, Address: {customer1.get_address()}")
    print(f"Order Status: {order1.get_status()}")
    print(f"Admin: {admin1.get_name()}, Phone: {admin1.get_phone_number()}")
    print(f"Delivery Staff: {staff1.get_name()}, Assigned Order: {staff1.get_assigned_orders()}")
    print(f"Item: {item1.get_name()}, Price: {item1.get_price()}, Stock: {item1.get_stock()}")






# **Smart Cart using IoT** 🛒

This project is a Smart Shopping Cart system that uses an ESP8266 microcontroller, a LiquidCrystal I2C display, and a web server to manage shopping cart operations like adding/removing items and displaying the total cost of purchased items.

The system connects to a Wi-Fi network and provides a local web interface to monitor the cart's contents. It also uses the RFID tag (or barcode) scanning system for adding or removing products.

---

## **📂 Project Files**

- `SmartCart.ino`  
  - Arduino code for the Smart Cart system.

---

## **🔧 Hardware Required**

- **ESP8266 NodeMCU** (or any compatible ESP8266 board)
- **LiquidCrystal I2C Display (16x2)**
- **RFID Reader** (or Barcode Scanner)
- **Buzzer** (Optional for feedback)
- **Breadboard and Connecting Wires**
- **Push-button for cart operations**
- **External Power Supply (if needed for the ESP8266)**

---

## **💻 Code Overview**

### **Setup**

1. **Wi-Fi Setup**:
   - The ESP8266 connects to a specified Wi-Fi network using `ssid` and `password`.

2. **LCD Display**:
   - The system uses an LCD screen to display messages like "Welcome", "Wi-Fi Connected", and "Please Add Items to Cart".

3. **Web Server**:
   - The ESP8266 acts as a web server, accessible via the local IP address after Wi-Fi connection is established.
   - A simple webpage is hosted to display the cart's contents, including the quantity and cost of each product.

### **Product Details**

- **Chocolate**: Rs 35.00
- **Milk**: Rs 38.00
- **Rice (1KG)**: Rs 55.00
- **Lays**: Rs 10.00

Each product has a specific code associated with it, and users can add or remove items by scanning the RFID tag (or barcode).

### **Adding and Removing Items**

- **Add Item**: When an item is added to the cart, the corresponding product’s quantity is increased, and the total cost is updated.
- **Remove Item**: When an item is removed, its quantity decreases, and the total cost is updated.
- **View Cart**: The cart contents are displayed on both the LCD and the web interface, showing the items, quantities, and prices.

### **Web Interface**

- A simple HTML page is served at the root URL of the ESP8266.
- The table shows the cart’s contents, including:
  - **Items** (e.g., Chocolate, Milk, Rice, Lays)
  - **Quantity**
  - **Cost**
  - **Grand Total**

You can also **Pay Now** through a button on the webpage (non-functional for this prototype).

### **Payment and Final Checkout**

Once the checkout button is clicked (web interface), the cart shows the total products and final price. The system then displays a "Thank You" message on the LCD.

---

## **⚙️ Code Explanation**

- **Wi-Fi Connection**: The ESP8266 connects to the Wi-Fi network defined by the `ssid` and `password` variables.
- **RFID (or Barcode) Scanning**: Each product (Chocolate, Milk, Rice, Lays) has a unique 12-character code. When a code is scanned, the corresponding item is either added or removed from the cart.
- **LCD Display**: The LCD is used to show the status of the cart (item added, item removed, total cost, etc.).
- **Web Interface**: The ESP8266 hosts a simple web page with a table showing the cart’s contents. The page auto-refreshes every 2 seconds to reflect the changes in real-time.
- **Buzzer**: A buzzer is optionally used to provide feedback whenever an item is added or removed.

---

## **🖥️ Web Interface Screenshot**

Here’s an example of how the webpage may look:

```html
<h1>Smart Shopping Cart</h1>
<table>
  <tr>
    <th>ITEMS</th>
    <th>QUANTITY</th>
    <th>COST</th>
  </tr>
  <tr>
    <td>Chocolate</td><td>1</td><td>35.00</td>
  </tr>
  <tr>
    <td>Milk</td><td>2</td><td>76.00</td>
  </tr>
  <tr>
    <td>Rice</td><td>1</td><td>55.00</td>
  </tr>
  <tr>
    <th>Grand Total</th><th>4</th><th>166.00</th>
  </tr>
</table>
<button>Pay Now</button>
```

---

## **⚠️ Notes**

- The system assumes RFID tags or barcodes are available to uniquely identify products.
- The webpage auto-refreshes every 2 seconds to show the updated cart status.
- This is a prototype for IoT-based cart management, and additional features (like mobile app integration, real-time inventory check, etc.) can be added for better functionality.

---

## **💡 Future Improvements**

- **Payment Integration**: Integrate with a payment gateway for online payments.
- **Mobile App**: Develop a mobile app for easier cart management.
- **Multiple Carts**: Handle multiple carts by assigning a unique ID to each cart.
- **Automatic Stock Update**: Connect to an inventory management system for real-time stock updates.

---

## **👨‍💻 Author**

- **Technical Tamizha**  
  - [Website](https://www.procreativehub.com)

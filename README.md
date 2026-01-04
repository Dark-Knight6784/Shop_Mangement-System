# PyShop: Inventory Management System

**PyShop** is a robust, command-line interface (CLI) application designed to simulate an e-commerce ecosystem. It features distinct interfaces for **Business Owners** and **Customers**, allowing for real-time inventory management, shopping cart processing, and automatic invoice generation.

The system ensures data persistence using JSON storage, ensuring stock levels are maintained between sessions.

---

## 🚀 Key Features

### 👑 Owner Interface (Admin)

* **Inventory Oversight:** View the complete product list including SKU, Name, Price, and current Stock levels.
* **Stock Management:** Add new products or update existing ones (Price/Quantity) dynamically via SKU.
* **Data Persistence:** All inventory changes are automatically saved to `pyshop_inventory.json`.

### 👨‍💼 Customer Interface

* **Interactive Shopping:** Browse products and add items to a personal shopping cart.
* **Smart Validation:** Prevents adding items that exceed available stock or entering invalid quantities.
* **Cart Management:** View current cart sub-totals and grand totals before purchasing.
* **Secure Checkout:**
* Validates final stock availability immediately before transaction completion.
* Updates the master inventory instantly upon purchase.



### 📄 Automated Invoicing

* Generates a detailed `.txt` receipt for every successful checkout.
* Receipts are timestamped (e.g., `Invoice_ID_20231025_123045.txt`) containing itemized breakdowns and total cost.

---

## 🛠️ Technical Architecture

The project is structured around three core classes:

1. **`Product`**: Defines the data structure for items (SKU, Name, Price, Stock) and handles serialization.
2. **`Cart`**: Manages the customer's session, handles item aggregation, calculates totals, and triggers the checkout process.
3. **`InventoryManager`**: Handles all File I/O operations (loading/saving JSON), enforces business logic (stock reduction), and initializes default data if no file exists.

---

## ⚙️ Installation & Setup

### Prerequisites

* Python 3.x
* Standard libraries used: `json`, `os`, `datetime`, `sys` (No external `pip` installations required).

### Running the Application

1. Download the script (`project_2nd semester.py`).
2. Open your terminal or command prompt.
3. Navigate to the directory containing the file.
4. Run the following command:

```bash
python "project_2nd semester.py"

```

*Note: On the first run, the system will automatically generate `pyshop_inventory.json` with default items (Laptops, Mice, Keyboards, etc.).*

---

## 📖 Usage Guide

Upon launching, select your user type from the main menu:

```text
🏠 PyShop Main Menu 🏠
Select User Type:
1. Owner👑
2. Customer👨
3. Exit👋

```

### For Owners

1. Select **Option 1**.
2. Choose **Add/Update Stock** to input new inventory.
* *Input:* SKU (e.g., SKU001), Name, Price, and Stock Quantity.


3. Changes are saved immediately upon confirmation.

### For Customers

1. Select **Option 2**.
2. View the inventory and note the **SKU** of the item you wish to buy.
3. Select **Shop** and enter the SKU and Quantity.
4. Select **Checkout** to finalize the order and generate your receipt.

---

## 📂 File Structure

```text
/project-directory
│
├── project_2nd semester.py    # Main application source code
├── pyshop_inventory.json      # Persistent database (Auto-generated)
├── Invoice_ID_XXXXXXXX.txt    # Customer receipts (Auto-generated)
└── README.md                  # Project documentation

```

---

## 🛡️ Error Handling

The application includes robust error handling for:

* **Invalid Inputs:** Protections against negative prices or stock values.
* **Overselling:** Prevents checkout if a user tries to buy more items than exist in the inventory.
* **File Corruption:** Handles JSON decode errors by resetting to a safe state.

---

## 📝 License

This project was developed for academic purposes. Feel free to modify and use it for learning Python file handling and OOP concepts.

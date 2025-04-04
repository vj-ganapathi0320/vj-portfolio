<!DOCTYPE html>
<html lang="ta">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hotel Food Ordering System</title>
  <style>
    /* General Styles */
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 20px;
    }
    h1, h2, h3 {
      color: #333;
    }
    ul {
      list-style: none;
      padding: 0;
    }
    li {
      margin: 10px 0;
    }
    button {
      padding: 5px 10px;
      margin-left: 10px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 3px;
      cursor: pointer;
    }
    button:hover {
      background-color: #218838;
    }
    select {
      padding: 5px;
      margin: 10px 0;
    }
    .hidden {
      display: none;
    }
    .nav {
      margin-bottom: 20px;
    }
    .nav button {
      margin-right: 10px;
    }
    .section {
      margin-top: 20px;
      padding: 15px;
      background: #fff;
      border-radius: 5px;
      box-shadow: 0 0 5px rgba(0,0,0,0.1);
    }
    
    /* Updated Rich Blue Admin (Bill) Section Styles */
    #bill-section {
      background: linear-gradient(135deg, #1e3c72, #2a5298);
      color: #f4f4f4;
    }
    #bill-section h2, #bill-section h3 {
      text-shadow: 1px 1px 2px #000;
    }
    #bill-header {
      display: flex;
      align-items: center;
      margin-bottom: 15px;
    }
    #bill-header img {
      width: 50px;
      height: 50px;
      margin-right: 15px;
    }
    #bill-header h2 {
      margin: 0;
    }
    
    /* Admin login modal style */
    .modal {
      position: fixed;        
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.5);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 10;
    }
    .modal-content {
      background: #fff;
      padding: 20px;
      border-radius: 5px;
      text-align: center;
      width: 300px;
    }
    .modal-content input {
      width: 80%;
      padding: 8px;
      margin-bottom: 10px;
    }
  </style>
</head>
<body>
  <h1>Hotel Food Ordering System</h1>
  
  <!-- Navigation Buttons -->
  <div class="nav">
    <button onclick="showSection('order')">Waiter (Order)</button>
    <button onclick="showSection('kitchen')">Kitchen</button>
    <button onclick="showSection('bill')">Admin (Bill)</button>
  </div>
  
  <!-- Order Section (Waiter Page) -->
  <div id="order-section" class="section">
    <h2>Order Page - Waiter</h2>
    <h3>Menu</h3>
    <ul id="menu-list">
      <li>Idly - ₹10 <button onclick="addToOrder('Idly', 10)">Order</button></li>
      <li>Dosa - ₹30 <button onclick="addToOrder('Dosa', 30)">Order</button></li>
      <li>Pongal - ₹40 <button onclick="addToOrder('Pongal', 40)">Order</button></li>
    </ul>
    <h3>Table Selection</h3>
    <select id="table-select">
      <option value="1">Table 1</option>
      <option value="2">Table 2</option>
      <option value="3">Table 3</option>
    </select>
    <h3>Order List</h3>
    <ul id="order-list"></ul>
    <button onclick="generateBill()">Generate Bill</button>
  </div>
  
  <!-- Kitchen Section -->
  <div id="kitchen-section" class="section hidden">
    <h2>Kitchen Page</h2>
    <h3>Pending Orders</h3>
    <ul id="pending-orders"></ul>
  </div>
  
  <!-- Bill (Admin) Section -->
  <div id="bill-section" class="section hidden">
    <div id="bill-header">
      <img src="logo.jpg" alt="Logo Icon">
      <h2>Admin/Biller Page</h2>
    </div>
    <h3>Bill Details</h3>
    <div id="bill-details">
      <!-- Bill details will appear here -->
    </div>
    <button onclick="downloadBill()">Download Bill as CSV</button>
    <h3>Manage Food Items</h3>
    <div id="manage-food">
      <p>(Food item management options can be added here.)</p>
    </div>
    <h3>Change Admin Password</h3>
    <div id="admin-password">
      <input type="password" id="admin-password-input" placeholder="Enter new password">
      <button onclick="changePassword()">Change Password</button>
    </div>
  </div>
  
  <!-- Admin Login Modal -->
  <div id="admin-modal" class="modal">
    <div class="modal-content">
      <h3>Admin Login</h3>
      <input type="password" id="admin-login-password" placeholder="Enter admin password">
      <br>
      <button onclick="verifyAdminPassword()">Login</button>
    </div>
  </div>
  
  <!-- JavaScript Code -->
  <script>
    // Global orders array for Order Page
    let orders = [];
    
    // Default admin password (if not set in localStorage)
    if (!localStorage.getItem('adminPassword')) {
      localStorage.setItem('adminPassword', 'admin123');
    }
    
    // Function to toggle sections
    function showSection(section) {
      // Hide all sections
      document.getElementById('order-section').classList.add('hidden');
      document.getElementById('kitchen-section').classList.add('hidden');
      document.getElementById('bill-section').classList.add('hidden');
      
      if(section === 'bill'){
        // When admin section selected, show admin login modal
        document.getElementById('admin-modal').style.display = 'flex';
      } else {
        // Directly show the selected section
        document.getElementById(section + '-section').classList.remove('hidden');
        if (section === 'kitchen') {
          loadPendingOrders();
        }
      }
    }
    
    // Verify admin password from modal
    function verifyAdminPassword() {
      const entered = document.getElementById('admin-login-password').value;
      const stored = localStorage.getItem('adminPassword');
      if(entered === stored) {
        // Hide modal and show admin page
        document.getElementById('admin-modal').style.display = 'none';
        document.getElementById('bill-section').classList.remove('hidden');
        showBillDetails();
      } else {
        alert('Invalid Password! Try again.');
      }
      document.getElementById('admin-login-password').value = '';
    }
    
    // Order Page Functions
    function addToOrder(food, price) {
      orders.push({ food, price });
      updateOrderList();
    }
    
    function updateOrderList() {
      const orderList = document.getElementById('order-list');
      orderList.innerHTML = '';
      orders.forEach((item) => {
        const li = document.createElement('li');
        li.textContent = item.food + ' - ₹' + item.price;
        orderList.appendChild(li);
      });
    }
    
    function generateBill() {
      const total = orders.reduce((sum, item) => sum + item.price, 0);
      const table = document.getElementById('table-select').value;
      
      const newOrder = {
        table: table,
        food: orders.map(item => item.food).join(', '),
        price: total
      };
      
      let pendingOrders = JSON.parse(localStorage.getItem('pendingOrders')) || [];
      pendingOrders.push(newOrder);
      localStorage.setItem('pendingOrders', JSON.stringify(pendingOrders));
      
      alert('Table ' + table + ' total bill: ₹' + total);
      orders = [];
      updateOrderList();
    }
    
    // Kitchen Page Functions
    function loadPendingOrders() {
      const pendingOrdersElem = document.getElementById('pending-orders');
      let pendingOrders = JSON.parse(localStorage.getItem('pendingOrders')) || [];
      pendingOrdersElem.innerHTML = '';
      
      if (pendingOrders.length === 0) {
        pendingOrdersElem.innerHTML = '<li>No pending orders</li>';
      } else {
        pendingOrders.forEach((order, index) => {
          const li = document.createElement('li');
          li.textContent = 'Table ' + order.table + ' - ' + order.food + ' - ₹' + order.price;
          const readyBtn = document.createElement('button');
          readyBtn.textContent = 'Ready';
          readyBtn.onclick = () => markAsReady(index);
          li.appendChild(readyBtn);
          pendingOrdersElem.appendChild(li);
        });
      }
    }
    
    function markAsReady(index) {
      let pendingOrders = JSON.parse(localStorage.getItem('pendingOrders')) || [];
      pendingOrders.splice(index, 1);
      localStorage.setItem('pendingOrders', JSON.stringify(pendingOrders));
      loadPendingOrders();
    }
    
    // Bill (Admin) Page Functions
    function showBillDetails() {
      const billDetailsElem = document.getElementById('bill-details');
      let pendingOrders = JSON.parse(localStorage.getItem('pendingOrders')) || [];
      billDetailsElem.innerHTML = '';
      
      if(pendingOrders.length === 0){
        billDetailsElem.innerHTML = '<p>No orders available</p>';
      } else {
        pendingOrders.forEach((order) => {
          const div = document.createElement('div');
          div.textContent = 'Table ' + order.table + ': ' + order.food + ' - ₹' + order.price;
          billDetailsElem.appendChild(div);
        });
      }
    }
    
    function downloadBill() {
      let pendingOrders = JSON.parse(localStorage.getItem('pendingOrders')) || [];
      let csvContent = "Table,Food,Price\n";
      pendingOrders.forEach(order => {
        csvContent += `${order.table},${order.food},${order.price}\n`;
      });
      
      const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
      const link = document.createElement('a');
      const url = URL.createObjectURL(blob);
      link.setAttribute('href', url);
      link.setAttribute('download', 'bill.csv');
      link.style.visibility = 'hidden';
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }
    
    function changePassword() {
      const newPassword = document.getElementById('admin-password-input').value;
      if (newPassword) {
        localStorage.setItem('adminPassword', newPassword);
        alert('Password changed successfully!');
      } else {
        alert('Please enter a new password.');
      }
      document.getElementById('admin-password-input').value = '';
    }
  </script>
</body>
</html>

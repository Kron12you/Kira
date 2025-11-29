<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ระบบจองอาหาร - โรงเรียน</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="style.css">
</head>
<body class="bg-gradient-to-br from-blue-50 to-indigo-100 min-h-screen">

<header class="bg-white shadow-lg">
  <div class="container mx-auto px-4 py-4 flex justify-between items-center">
    <h1 class="text-2xl font-bold text-indigo-800">🏫 ระบบจองอาหาร</h1>
    <div class="flex gap-2">
      <button onclick="showStudentLogin()" class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg">นักเรียน</button>
      <button onclick="showTeacherLogin()" class="bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg">ครู</button>
      <button onclick="showAdminLogin()" class="bg-purple-500 hover:bg-purple-600 text-white px-4 py-2 rounded-lg">แอดมิน</button>
    </div>
  </div>
</header>

<!-- Login Sections -->
<div id="studentLogin" class="container mx-auto px-4 py-8">
  <div class="max-w-md mx-auto bg-white rounded-xl shadow-lg p-6">
    <h2 class="text-xl font-bold text-center mb-4">เข้าสู่ระบบนักเรียน</h2>
    <input id="studentName" placeholder="ชื่อนักเรียน" class="w-full mb-2 px-3 py-2 border rounded-lg">
    <button onclick="studentLogin()" class="w-full bg-blue-500 hover:bg-blue-600 text-white py-2 rounded-lg">เข้าสู่ระบบ</button>
  </div>
</div>

<div id="dashboard" class="container mx-auto px-4 py-8 hidden">
  <h2 class="text-xl font-bold mb-4">สวัสดี <span id="userName"></span></h2>

  <div class="bg-white rounded-xl shadow-lg p-6 mb-6">
    <h3 class="font-bold text-lg mb-4">🍽️ เมนูอาหาร</h3>
    <div id="foodMenu" class="grid grid-cols-2 md:grid-cols-3 gap-4">
      <!-- Food items -->
    </div>
  </div>

  <div class="bg-white rounded-xl shadow-lg p-6">
    <h3 class="font-bold text-lg mb-4">🛒 ตะกร้าของคุณ</h3>
    <div id="cartItems" class="space-y-2">
      <p class="text-gray-500 text-center">ยังไม่มีรายการในตะกร้า</p>
    </div>
    <div class="flex justify-between items-center mt-4">
      <span class="font-bold">รวมทั้งหมด:</span>
      <span class="text-xl font-bold text-blue-600">฿<span id="cartTotal">0</span></span>
    </div>
    <button onclick="checkout()" class="w-full mt-3 bg-green-500 hover:bg-green-600 text-white py-2 rounded-lg">ชำระเงิน</button>
  </div>
</div>

<!-- Payment Page -->
<div id="paymentPage" class="container mx-auto px-4 py-8 hidden">
  <div class="max-w-md mx-auto bg-white rounded-xl shadow-lg p-6">
    <h2 class="text-xl font-bold text-center mb-4">💳 ชำระเงิน</h2>
    <p class="text-lg mb-2">ยอดชำระ: ฿<span id="paymentTotal">0</span></p>
    <p class="text-sm mb-2">รายการที่สั่ง: <span id="paymentItemsCount">0</span> รายการ</p>
    <input type="file" id="paymentProof" accept="image/*" capture="environment" class="w-full mb-2 px-3 py-2 border rounded-lg">
    <button onclick="confirmPayment()" class="w-full bg-green-500 hover:bg-green-600 text-white py-2 rounded-lg">ยืนยันชำระเงิน</button>
    <button onclick="backToDashboard()" class="w-full mt-2 bg-gray-500 hover:bg-gray-600 text-white py-2 rounded-lg">ย้อนกลับ</button>
  </div>
</div>

<script src="script.js"></script>
</body>
</html>

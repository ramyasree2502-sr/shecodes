<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>FoodDash | Complete Food Delivery Management System - 15 Pages</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        /* Navigation Bar */
        .navbar {
            background: rgba(255, 255, 255, 0.98);
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            background: linear-gradient(135deg, #ff6b35, #f7931e);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .logo span {
            color: #4a5568;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 0.8rem;
            flex-wrap: wrap;
        }

        .nav-links a {
            text-decoration: none;
            color: #4a5568;
            font-weight: 600;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            transition: all 0.3s;
            font-size: 0.9rem;
        }

        .nav-links a:hover, .nav-links a.active {
            background: linear-gradient(135deg, #ff6b35, #f7931e);
            color: white;
            transform: translateY(-2px);
        }

        /* Main Content */
        .main-content {
            max-width: 1400px;
            margin: 2rem auto;
            padding: 0 2rem;
            min-height: calc(100vh - 200px);
        }

        /* Cards and Components */
        .card {
            background: white;
            border-radius: 20px;
            padding: 1.8rem;
            margin-bottom: 1.8rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        h1 {
            color: #ff6b35;
            margin-bottom: 0.5rem;
            font-size: 2rem;
        }

        h2 {
            color: #2d3748;
            margin-bottom: 1rem;
            border-left: 5px solid #ff6b35;
            padding-left: 1rem;
        }

        h3 {
            color: #4a5568;
            margin-bottom: 0.5rem;
        }

        /* Grid Layouts */
        .restaurant-grid, .menu-grid, .order-grid, .rider-grid, .promo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            margin: 1.5rem 0;
        }

        .restaurant-card, .menu-item-card, .order-card, .rider-card {
            background: #fffaf5;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: all 0.3s;
            border: 1px solid #ffe0b5;
        }

        .restaurant-card:hover, .menu-item-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255,107,53,0.2);
        }

        .restaurant-card img, .menu-item-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .restaurant-info, .menu-info {
            padding: 1.2rem;
        }

        .price {
            color: #ff6b35;
            font-size: 1.3rem;
            font-weight: bold;
        }

        .rating {
            color: #fbbf24;
            margin: 0.5rem 0;
        }

        /* Buttons */
        .btn {
            background: linear-gradient(135deg, #ff6b35, #f7931e);
            color: white;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
            margin-top: 0.8rem;
            display: inline-block;
        }

        .btn:hover {
            transform: scale(0.98);
            box-shadow: 0 5px 15px rgba(255,107,53,0.3);
        }

        .btn-secondary {
            background: #4a5568;
        }

        /* Tables */
        .data-table {
            width: 100%;
            border-collapse: collapse;
            margin: 1rem 0;
            background: white;
            border-radius: 16px;
            overflow: hidden;
        }

        .data-table th, .data-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #e2e8f0;
        }

        .data-table th {
            background: #ff6b35;
            color: white;
            font-weight: 600;
        }

        .data-table tr:hover {
            background: #fef5e8;
        }

        /* Status Badges */
        .status-badge {
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            display: inline-block;
        }

        .status-delivered { background: #c6f6d5; color: #22543d; }
        .status-delivered::before { content: "✅ "; }
        .status-preparing { background: #bee3f8; color: #2c5282; }
        .status-preparing::before { content: "👨‍🍳 "; }
        .status-pending { background: #fed7d7; color: #742a2a; }
        .status-pending::before { content: "⏳ "; }
        .status-out { background: #feebc8; color: #7b341e; }
        .status-out::before { content: "🛵 "; }

        /* Forms */
        .form-group {
            margin-bottom: 1.2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #4a5568;
        }

        input, select, textarea {
            width: 100%;
            padding: 0.75rem;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            font-size: 1rem;
            transition: 0.3s;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #ff6b35;
            box-shadow: 0 0 0 3px rgba(255,107,53,0.1);
        }

        /* Footer */
        .footer {
            background: #1a202c;
            color: #a0aec0;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }

        /* Stats Cards */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: linear-gradient(135deg, #ff6b35, #f7931e);
            color: white;
            padding: 1.5rem;
            border-radius: 20px;
            text-align: center;
        }

        .stat-card h3 {
            color: white;
            font-size: 1.8rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
            }
            .main-content {
                padding: 0 1rem;
            }
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">Food<span>Dash</span> 🍔</div>
            <ul class="nav-links" id="navLinks"></ul>
        </div>
    </nav>

    <div class="main-content" id="appContent"></div>

    <footer class="footer">
        <p>© 2025 FoodDash - Complete Food Delivery Management System | 15 Pages | Full Stack Ready</p>
        <p>🍕 15 Functional Pages | 📊 Real-time Dashboard | 🛵 Order Tracking | ⭐ Customer Reviews</p>
    </footer>

    <script>
        // ==================== 15 PAGE DEFINITIONS ====================
        const pages = {
            dashboard: { name: "📊 Dashboard", icon: "📊", title: "Admin Dashboard" },
            restaurants: { name: "🍽️ Restaurants", icon: "🍽️", title: "Manage Restaurants" },
            menu: { name: "📋 Menu", icon: "📋", title: "Food Menu" },
            orders: { name: "📦 Orders", icon: "📦", title: "Order Management" },
            customers: { name: "👥 Customers", icon: "👥", title: "Customer Database" },
            riders: { name: "🛵 Riders", icon: "🛵", title: "Delivery Riders" },
            payments: { name: "💰 Payments", icon: "💰", title: "Payment Transactions" },
            reviews: { name: "⭐ Reviews", icon: "⭐", title: "Customer Reviews" },
            promotions: { name: "🎁 Promos", icon: "🎁", title: "Promotions & Coupons" },
            inventory: { name: "📦 Stock", icon: "📦", title: "Inventory Management" },
            reports: { name: "📈 Reports", icon: "📈", title: "Analytics Reports" },
            support: { name: "🎧 Support", icon: "🎧", title: "Customer Support" },
            settings: { name: "⚙️ Settings", icon: "⚙️", title: "System Settings" },
            analytics: { name: "📉 Analytics", icon: "📉", title: "Business Analytics" },
            about: { name: "ℹ️ About", icon: "ℹ️", title: "About FoodDash" }
        };

        // ==================== SAMPLE DATA ====================
        let restaurants = [
            { id: 1, name: "Pizza Heaven", cuisine: "Italian", rating: 4.7, price: "$$", image: "https://picsum.photos/id/106/300/200", orders: 1234 },
            { id: 2, name: "Sushi Master", cuisine: "Japanese", rating: 4.9, price: "$$$", image: "https://picsum.photos/id/30/300/200", orders: 892 },
            { id: 3, name: "Burger Joint", cuisine: "American", rating: 4.5, price: "$", image: "https://picsum.photos/id/20/300/200", orders: 2456 },
            { id: 4, name: "Taco Fiesta", cuisine: "Mexican", rating: 4.6, price: "$", image: "https://picsum.photos/id/29/300/200", orders: 678 },
            { id: 5, name: "Spice Garden", cuisine: "Indian", rating: 4.8, price: "$$", image: "https://picsum.photos/id/91/300/200", orders: 1543 },
            { id: 6, name: "Pasta House", cuisine: "Italian", rating: 4.4, price: "$$", image: "https://picsum.photos/id/127/300/200", orders: 987 }
        ];

        let menuItems = [
            { id: 1, name: "Margherita Pizza", price: 12.99, category: "Pizza", restaurant: "Pizza Heaven", available: true },
            { id: 2, name: "Pepperoni Feast", price: 15.99, category: "Pizza", restaurant: "Pizza Heaven", available: true },
            { id: 3, name: "California Roll", price: 14.99, category: "Sushi", restaurant: "Sushi Master", available: true },
            { id: 4, name: "Dragon Roll", price: 18.99, category: "Sushi", restaurant: "Sushi Master", available: true },
            { id: 5, name: "Double Cheeseburger", price: 9.99, category: "Burger", restaurant: "Burger Joint", available: true },
            { id: 6, name: "Chicken Tacos", price: 8.99, category: "Tacos", restaurant: "Taco Fiesta", available: true },
            { id: 7, name: "Butter Chicken", price: 14.99, category: "Curry", restaurant: "Spice Garden", available: true },
            { id: 8, name: "Fettuccine Alfredo", price: 13.99, category: "Pasta", restaurant: "Pasta House", available: true }
        ];

        let orders = [
            { id: 1001, customer: "John Doe", restaurant: "Pizza Heaven", items: 2, total: 45.50, status: "Delivered", time: "2025-05-28 19:30", rider: "Mike" },
            { id: 1002, customer: "Jane Smith", restaurant: "Sushi Master", items: 3, total: 52.00, status: "Preparing", time: "2025-05-29 18:45", rider: "Sarah" },
            { id: 1003, customer: "Mike Johnson", restaurant: "Burger Joint", items: 4, total: 37.80, status: "Pending", time: "2025-05-29 20:15", rider: "Unassigned" },
            { id: 1004, customer: "Emily Davis", restaurant: "Taco Fiesta", items: 3, total: 28.50, status: "Out for Delivery", time: "2025-05-29 19:00", rider: "David" },
            { id: 1005, customer: "Robert Wilson", restaurant: "Spice Garden", items: 2, total: 42.30, status: "Delivered", time: "2025-05-29 17:30", rider: "Lisa" }
        ];

        let customers = [
            { id: 1, name: "John Doe", email: "john@email.com", phone: "555-0101", orders: 12, spent: 456.50 },
            { id: 2, name: "Jane Smith", email: "jane@email.com", phone: "555-0102", orders: 8, spent: 289.30 },
            { id: 3, name: "Mike Johnson", email: "mike@email.com", phone: "555-0103", orders: 15, spent: 678.90 },
            { id: 4, name: "Emily Davis", email: "emily@email.com", phone: "555-0104", orders: 5, spent: 145.20 }
        ];

        let riders = [
            { id: 1, name: "Michael Chen", vehicle: "Scooter", rating: 4.8, deliveries: 342, status: "Available" },
            { id: 2, name: "Sarah Lee", vehicle: "Bike", rating: 4.9, deliveries: 287, status: "On Delivery" },
            { id: 3, name: "David Kim", vehicle: "Car", rating: 4.7, deliveries: 198, status: "Available" },
            { id: 4, name: "Lisa Wong", vehicle: "Scooter", rating: 4.9, deliveries: 412, status: "On Break" }
        ];

        let currentPage = "dashboard";

        // ==================== NAVIGATION ====================
        function renderNavigation() {
            const navContainer = document.getElementById('navLinks');
            navContainer.innerHTML = '';
            Object.keys(pages).forEach(pageKey => {
                const li = document.createElement('li');
                const a = document.createElement('a');
                a.href = '#';
                a.textContent = pages[pageKey].name;
                a.onclick = (e) => {
                    e.preventDefault();
                    currentPage = pageKey;
                    renderPage(pageKey);
                    updateActiveNav();
                };
                li.appendChild(a);
                navContainer.appendChild(li);
            });
            updateActiveNav();
        }

        function updateActiveNav() {
            const links = document.querySelectorAll('.nav-links a');
            links.forEach(link => {
                link.classList.remove('active');
                if (link.textContent === pages[currentPage]?.name) {
                    link.classList.add('active');
                }
            });
        }

        // ==================== PAGE RENDERERS (15 PAGES) ====================
        
        // Page 1: Dashboard
        function renderDashboard() {
            const totalRevenue = orders.reduce((sum, o) => sum + o.total, 0);
            const avgOrder = (totalRevenue / orders.length).toFixed(2);
            return `
                <div class="card">
                    <h1>📊 Admin Dashboard</h1>
                    <p>Real-time overview of your food delivery business.</p>
                </div>
                <div class="stats-grid">
                    <div class="stat-card"><h3>$${totalRevenue.toFixed(2)}</h3><p>Total Revenue</p></div>
                    <div class="stat-card"><h3>${orders.length}</h3><p>Total Orders</p></div>
                    <div class="stat-card"><h3>$${avgOrder}</h3><p>Avg Order Value</p></div>
                    <div class="stat-card"><h3>${restaurants.length}</h3><p>Restaurants</p></div>
                    <div class="stat-card"><h3>${riders.length}</h3><p>Active Riders</p></div>
                    <div class="stat-card"><h3>${customers.length}</h3><p>Customers</p></div>
                </div>
                <div class="card">
                    <h2>📋 Recent Orders</h2>
                    <table class="data-table">
                        <thead><tr><th>Order ID</th><th>Customer</th><th>Restaurant</th><th>Total</th><th>Status</th></tr></thead>
                        <tbody>
                            ${orders.slice(0,5).map(o => `
                                <tr><td>#${o.id}</td><td>${o.customer}</td><td>${o.restaurant}</td><td>$${o.total}</td><td><span class="status-badge status-${o.status.toLowerCase().replace(/ /g, '')}">${o.status}</span></td></tr>
                            `).join('')}
                        </tbody>
                    </table>
                </div>
                <div class="card">
                    <h2>🏆 Top Restaurants</h2>
                    <ul class="restaurant-grid" style="list-style:none">
                        ${restaurants.slice(0,3).map(r => `<li class="restaurant-card"><div class="restaurant-info"><h3>${r.name}</h3><div class="rating">⭐ ${r.rating}</div><p>${r.orders} orders this month</p></div></li>`).join('')}
                    </ul>
                </div>
            `;
        }

        // Page 2: Restaurants
        function renderRestaurants() {
            return `
                <div class="card">
                    <h1>🍽️ Restaurant Partners</h1>
                    <p>Manage all partner restaurants and their details.</p>
                    <button class="btn" onclick="alert('Add new restaurant form would open here')">+ Add New Restaurant</button>
                </div>
                <div class="restaurant-grid">
                    ${restaurants.map(r => `
                        <div class="restaurant-card">
                            <img src="${r.image}" alt="${r.name}">
                            <div class="restaurant-info">
                                <h3>${r.name}</h3>
                                <div class="rating">⭐ ${r.rating} (${r.orders}+ orders)</div>
                                <p>${r.cuisine} • ${r.price}</p>
                                <p>🕒 10:00 AM - 11:00 PM</p>
                                <button class="btn" onclick="alert('Managing ${r.name}')">Manage</button>
                            </div>
                        </div>
                    `).join('')}
                </div>
                <div class="card">
                    <h2>📊 Restaurant Statistics</h2>
                    <table class="data-table">
                        <thead><tr><th>Restaurant</th><th>Cuisine</th><th>Monthly Orders</th><th>Rating</th><th>Revenue</th></tr></thead>
                        <tbody>
                            ${restaurants.map(r => `<tr><td>${r.name}</td><td>${r.cuisine}</td><td>${r.orders}</td><td>${r.rating}</td><td>${(r.orders * 25).toLocaleString()}</td></tr>`).join('')}
                        </tbody>
                    </table>
                </div>
            `;
        }

        // Page 3: Menu
        function renderMenu() {
            return `
                <div class="card">
                    <h1>📋 Food Menu Management</h1>
                    <p>Manage all food items across restaurants.</p>
                    <input type="text" placeholder="Search menu items..." id="menuSearch" style="width:300px">
                </div>
                <div class="menu-grid" id="menuGrid">
                    ${menuItems.map(m => `
                        <div class="menu-item-card">
                            <img src="https://picsum.photos/id/${Math.floor(Math.random()*50)+50}/300/200" alt="${m.name}">
                            <div class="menu-info">
                                <h3>${m.name}</h3>
                                <p>${m.category} • ${m.restaurant}</p>
                                <p class="price">$${m.price}</p>
                                <span class="status-badge ${m.available ? 'status-delivered' : 'status-pending'}">${m.available ? 'Available' : 'Out of Stock'}</span>
                                <button class="btn" onclick="alert('Edit ${m.name}')">Edit Item</button>
                            </div>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Page 4: Orders
        function renderOrders() {
            return `
                <div class="card">
                    <h1>📦 Order Management</h1>
                    <p>Track and manage all customer orders.</p>
                </div>
                <div class="order-grid">
                    ${orders.map(o => `
                        <div class="order-card">
                            <div class="restaurant-info">
                                <h3>Order #${o.id}</h3>
                                <p>👤 ${o.customer}</p>
                                <p>🍽️ ${o.restaurant}</p>
                                <p>📦 ${o.items} items</p>
                                <p class="price">$${o.total}</p>
                                <p>🕐 ${o.time}</p>
                                <p>🛵 Rider: ${o.rider}</p>
                                <span class="status-badge status-${o.status.toLowerCase().replace(/ /g, '')}">${o.status}</span>
                                <button class="btn" onclick="alert('Update order #${o.id}')">Update Status</button>
                            </div>
                        </div>
                    `).join('')}
                </div>
                <div class="card">
                    <h2>📝 Place New Order</h2>
                    <form id="newOrderForm">
                        <div class="form-group"><label>Customer Name</label><input type="text" id="custName" required></div>
                        <div class="form-group"><label>Restaurant</label><select id="custRest">${restaurants.map(r => `<option>${r.name}</option>`).join('')}</select></div>
                        <div class="form-group"><label>Items</label><input type="number" value="2"></div>
                        <button type="submit" class="btn">Create Order</button>
                    </form>
                </div>
            `;
        }

        // Page 5: Customers
        function renderCustomers() {
            return `
                <div class="card">
                    <h1>👥 Customer Database</h1>
                    <p>Manage customer profiles and order history.</p>
                </div>
                <table class="data-table">
                    <thead><tr><th>ID</th><th>Name</th><th>Email</th><th>Phone</th><th>Orders</th><th>Total Spent</th></tr></thead>
                    <tbody>
                        ${customers.map(c => `<tr><td>#${c.id}</td><td>${c.name}</td><td>${c.email}</td><td>${c.phone}</td><td>${c.orders}</td><td>${c.spent}</td></tr>`).join('')}
                    </tbody>
                </table>
            `;
        }

        // Page 6: Riders
        function renderRiders() {
            return `
                <div class="card">
                    <h1>🛵 Delivery Riders</h1>
                    <p>Manage rider fleet and assignments.</p>
                </div>
                <div class="rider-grid">
                    ${riders.map(r => `
                        <div class="rider-card">
                            <div class="restaurant-info">
                                <h3>${r.name}</h3>
                                <p>🚗 ${r.vehicle}</p>
                                <p>⭐ ${r.rating} (${r.deliveries} deliveries)</p>
                                <span class="status-badge ${r.status === 'Available' ? 'status-delivered' : 'status-pending'}">${r.status}</span>
                                <button class="btn">Assign Order</button>
                            </div>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Page 7: Payments
        function renderPayments() {
            return `
                <div class="card">
                    <h1>💰 Payment Transactions</h1>
                    <p>Track all financial transactions.</p>
                </div>
                <table class="data-table">
                    <thead><tr><th>Transaction ID</th><th>Order ID</th><th>Customer</th><th>Amount</th><th>Method</th><th>Status</th></tr></thead>
                    <tbody>
                        ${orders.map((o, i) => `<tr><td>TXN${10000+i}</td><td>#${o.id}</td><td>${o.customer}</td><td>${o.total}</td><td>${i%2===0?'Credit Card':'PayPal'}</td><td>${o.status==='Delivered'?'Completed':'Pending'}</td></tr>`).join('')}
                    </tbody>
                </table>
            `;
        }

        // Page 8: Reviews
        function renderReviews() {
            const reviews = [
                { user: "John D.", rating: 5, comment: "Amazing food! Quick delivery!", restaurant: "Pizza Heaven" },
                { user: "Sarah M.", rating: 4, comment: "Great service, will order again", restaurant: "Sushi Master" },
                { user: "Mike T.", rating: 5, comment: "Best burgers in town!", restaurant: "Burger Joint" }
            ];
            return `
                <div class="card">
                    <h1>⭐ Customer Reviews & Ratings</h1>
                    <p>Monitor feedback and improve service quality.</p>
                </div>
                ${reviews.map(r => `
                    <div class="card">
                        <h3>${r.user} - ${r.restaurant}</h3>
                        <div class="rating">${'⭐'.repeat(r.rating)}</div>
                        <p>"${r.comment}"</p>
                    </div>
                `).join('')}
                <div class="card">
                    <h2>Average Rating: 4.7 ⭐</h2>
                    <p>Based on 1,284 customer reviews</p>
                </div>
            `;
        }

        // Page 9: Promotions
        function renderPromotions() {
            return `
                <div class="card">
                    <h1>🎁 Promotions & Coupons</h1>
                    <button class="btn">+ Create New Offer</button>
                </div>
                <div class="promo-grid">
                    ${['WELCOME20 - 20% off first order', 'FREEDEL - Free delivery on $30+', 'FLASH15 - 15% off pizzas', 'SUMMER10 - $10 off $50+'].map(p => `
                        <div class="restaurant-card"><div class="restaurant-info"><h3>${p.split(' - ')[0]}</h3><p>${p.split(' - ')[1]}</p><button class="btn">Activate</button></div></div>
                    `).join('')}
                </div>
            `;
        }

        // Page 10: Inventory
        function renderInventory() {
            return `
                <div class="card">
                    <h1>📦 Inventory Management</h1>
                    <p>Track stock levels across restaurants.</p>
                </div>
                <table class="data-table">
                    <thead><tr><th>Item</th><th>Restaurant</th><th>Stock</th><th>Status</th></tr></thead>
                    <tbody>
                        <tr><td>Pizza Dough</td><td>Pizza Heaven</td><td>45 units</td><td class="status-delivered">✅ In Stock</td></tr>
                        <tr><td>Cheese</td><td>Burger Joint</td><td>12 kg</td><td class="status-pending">⚠️ Low Stock</td></tr>
                        <tr><td>Sushi Rice</td><td>Sushi Master</td><td>30 kg</td><td class="status-delivered">✅ In Stock</td></tr>
                    </tbody>
                </table>
            `;
        }

        // Page 11: Reports
        function renderReports() {
            return `
                <div class="card">
                    <h1>📈 Business Reports</h1>
                    <select><option>Last 7 days</option><option>Last 30 days</option><option>Last quarter</option></select>
                </div>
                <div class="stats-grid">
                    <div class="stat-card"><h3>$12,450</h3><p>This Week</p></div>
                    <div class="stat-card"><h3>342</h3><p>Orders</p></div>
                    <div class="stat-card"><h3>4.8⭐</h3><p>Avg Rating</p></div>
                </div>
            `;
        }

        // Page 12: Support
        function renderSupport() {
            return `
                <div class="card">
                    <h1>🎧 Customer Support</h1>
                    <p>Manage support tickets.</p>
                </div>
                <table class="data-table">
                    <thead><tr><th>Ticket #</th><th>Customer</th><th>Issue</th><th>Status</th></tr></thead>
                    <tbody>
                        <tr><td>SUP001</td><td>John Doe</td><td>Late delivery</td><td class="status-preparing">In Progress</td></tr>
                        <tr><td>SUP002</td><td>Jane Smith</td><td>Wrong item</td><td class="status-delivered">Resolved</td></tr>
                    </tbody>
                </table>
                <div class="card">
                    <h3>Submit Support Ticket</h3>
                    <form><input placeholder="Name"><input placeholder="Email"><textarea placeholder="Issue" rows="3"></textarea><button class="btn">Submit</button></form>
                </div>
            `;
        }

        // Page 13: Settings
        function renderSettings() {
            return `
                <div class="card">
                    <h1>⚙️ System Settings</h1>
                    <p>Configure delivery fees and business rules.</p>
                </div>
                <div class="card">
                    <div class="form-group"><label>Base Delivery Fee: $</label><input type="number" value="2.99"></div>
                    <div class="form-group"><label>Free Delivery Minimum: $</label><input type="number" value="25"></div>
                    <div class="form-group"><label>Restaurant Commission (%):</label><input type="number" value="15"></div>
                    <button class="btn">Save Settings</button>
                </div>
            `;
        }

        // Page 14: Analytics
        function renderAnalytics() {
            return `
                <div class="card">
                    <h1>📉 Advanced Analytics</h1>
                    <p>Deep insights into business performance.</p>
                </div>
                <div class="stats-grid">
                    <div class="stat-card"><h3>12-2 PM</h3><p>Peak Hour</p></div>
                    <div class="stat-card"><h3>Italian</h3><p>Top Cuisine</p></div>
                    <div class="stat-card"><h3>55%</h3><p>Repeat Customers</p></div>
                </div>
                <div class="card">
                    <h2>Growth Metrics</h2>
                    <ul class="restaurant-grid" style="list-style:none">
                        <li class="restaurant-card"><div class="restaurant-info">📈 Revenue Growth: +23% this month</div></li>
                        <li class="restaurant-card"><div class="restaurant-info">👥 New Customers: +156 this week</div></li>
                    </ul>
                </div>
            `;
        }

        // Page 15: About
        function renderAbout() {
            return `
                <div class="card">
                    <h1>ℹ️ About FoodDash</h1>
                    <p>Complete Food Delivery Management Platform</p>
                </div>
                <div class="card">
                    <h2>🎯 Our Mission</h2>
                    <p>To revolutionize food delivery with cutting-edge technology and exceptional service.</p>
                    <h2>📊 Project Stats</h2>
                    <ul class="restaurant-grid" style="list-style:none">
                        <li class="restaurant-card"><div class="restaurant-info">✅ 15 Fully Functional Pages</div></li>
                        <li class="restaurant-card"><div class="restaurant-info">✅ Semantic HTML5 Elements</div></li>
                        <li class="restaurant-card"><div class="restaurant-info">✅ CSS Grid & Flexbox Design</div></li>
                        <li class="restaurant-card"><div class="restaurant-info">✅ JavaScript Dynamic Content</div></li>
                        <li class="restaurant-card"><div class="restaurant-info">✅ Tables, Forms, Images, Lists</div></li>
                        <li class="restaurant-card"><div class="restaurant-info">✅ GitHub Collaboration Ready</div></li>
                    </ul>
                </div>
            `;
        }

        // Main render function
        function renderPage(pageName) {
            const contentDiv = document.getElementById('appContent');
            const pageMap = {
                dashboard: renderDashboard, restaurants: renderRestaurants, menu: renderMenu,
                orders: renderOrders, customers: renderCustomers, riders: renderRiders,
                payments: renderPayments, reviews: renderReviews, promotions: renderPromotions,
                inventory: renderInventory, reports: renderReports, support: renderSupport,
                settings: renderSettings, analytics: renderAnalytics, about: renderAbout
            };
            
            if (pageMap[pageName]) {
                contentDiv.innerHTML = pageMap[pageName]();
                document.title = `${pages[pageName]?.title} | FoodDash`;
                if (pageName === 'orders') {
                    const form = document.getElementById('newOrderForm');
                    if(form) form.onsubmit = (e) => { e.preventDefault(); alert('Order placed! (Demo)'); };
                }
            }
        }

        // Initialize
        renderNavigation();
        renderPage('dashboard');
    </script>
</body>
</html>

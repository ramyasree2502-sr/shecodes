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

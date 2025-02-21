<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Find My Hostel (NSO)</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        /* Basic Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f4f7fc;
            color: #333;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 10px 20px;
            text-align: center;
        }

        header h1 {
            font-size: 2.5rem;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            margin-top: 10px;
        }

        nav ul li {
            margin: 0 20px;
        }

        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-size: 1.1rem;
        }

        nav ul li a:hover {
            color: #ff9900;
        }

        section {
            padding: 40px 20px;
            text-align: center;
        }

        #search-filters form {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            display: grid;
            gap: 15px;
            max-width: 600px;
            margin: 0 auto;
        }

        #search-filters input,
        #search-filters select,
        #search-filters button {
            padding: 10px;
            width: 100%;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #search-filters button {
            background-color: #333;
            color: #fff;
            font-size: 1.1rem;
            cursor: pointer;
        }

        #search-filters button:hover {
            background-color: #ff9900;
        }

        #featured-listings {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .listing-card {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            width: 250px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            text-align: left;
        }

        .listing-card img {
            width: 100%;
            border-radius: 8px;
            height: 150px;
            object-fit: cover;
        }

        .listing-card h3 {
            font-size: 1.4rem;
            margin: 10px 0;
        }

        .listing-card p {
            font-size: 1rem;
            margin-bottom: 8px;
        }

        .listing-card button {
            background-color: #333;
            color: #fff;
            padding: 10px;
            width: 100%;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .listing-card button:hover {
            background-color: #ff9900;
        }

        footer {
            background-color: #333;
            color: #fff;
            padding: 10px;
            text-align: center;
            margin-top: 40px;
        }

        footer a {
            color: #fff;
            text-decoration: none;
            margin: 0 10px;
        }

        footer a:hover {
            color: #ff9900;
        }

        /* Admin Panel */
        #admin-panel form {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            margin: 20px auto;
        }

        #admin-panel label {
            font-weight: bold;
        }

        #admin-panel input,
        #admin-panel select,
        #admin-panel button {
            width: 100%;
            margin: 10px 0;
        }

        /* Social Media */
        #social-media a {
            color: #333;
            font-size: 1.2rem;
            text-decoration: none;
            margin: 10px;
        }

        #social-media a:hover {
            color: #ff9900;
        }

        /* Booking Form */
        #booking form {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            margin: 20px auto;
        }

        #booking label {
            font-weight: bold;
        }
    </style>
</head>

<body>

    <header>
        <h1>Find My Hostel (NSO)</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#hostels">Hostels</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="search-filters">
        <h2>Search for Hostels</h2>
        <form action="/search" method="GET">
            <label for="location">Location:</label>
            <input type="text" id="location" name="location" placeholder="City, Area">

            <label for="rent-range">Rent Range:</label>
            <input type="number" id="min-rent" name="min-rent" placeholder="Min Rent">
            <input type="number" id="max-rent" name="max-rent" placeholder="Max Rent">

            <label for="accommodation-type">Accommodation Type:</label>
            <select id="accommodation-type" name="accommodation-type">
                <option value="single">Single</option>
                <option value="shared">Shared</option>
                <option value="pg">PG</option>
            </select>

            <label for="facilities">Facilities:</label>
            <input type="checkbox" id="wifi" name="facilities" value="Wi-Fi"> Wi-Fi
            <input type="checkbox" id="food" name="facilities" value="Food"> Food
            <input type="checkbox" id="ac" name="facilities" value="AC"> AC
            <input type="checkbox" id="gym" name="facilities" value="Gym"> Gym

            <label for="gender">Gender-specific:</label>
            <select id="gender" name="gender">
                <option value="any">Any</option>
                <option value="boys">Boys</option>
                <option value="girls">Girls</option>
            </select>

            <button type="submit">Search</button>
        </form>
    </section>

    <section id="hostel-listings">
        <h2>Hostel Listings</h2>
        <div class="listing-card">
            <img src="hostel1.jpg" alt="Hostel Image">
            <h3>Hostel Name</h3>
            <p>Location: City, Area</p>
            <p>Rent: ₹5000/month</p>
            <p>Amenities: Wi-Fi, Food, AC, Gym</p>
            <p>Gender: Boys</p>
            <button onclick="bookHostel()">Book Now</button>
        </div>
        <!-- Repeat for each hostel listing -->
    </section>

    <section id="booking">
        <h2>Book Hostel</h2>
        <form action="/book" method="POST">
            <label for="hostel-name">Hostel Name:</label>
            <input type="text" id="hostel-name" name="hostel-name" readonly>

            <label for="user-name">Your Name:</label>
            <input type="text" id="user-name" name="user-name" required>

            <label for="contact">Contact Number:</label>
            <input type="tel" id="contact" name="contact" required>

            <button type="submit">Book Now</button>
        </form>
    </section>

    <section id="admin-panel">
        <h2>Admin Dashboard</h2>
        <form action="/admin/update" method="POST">
            <label for="hostel-name">Hostel Name:</label>
            <input type="text" id="hostel-name" name="hostel-name" required>

            <label for="location">Location:</label>
            <input type="text" id="location" name="location" required>

            <label for="rent">Rent:</label>
            <input type="number" id="rent" name="rent" required>

            <label for="accommodation-type">Accommodation Type:</label>
            <select id="accommodation-type" name="accommodation-type" required>
                <option value="single">Single</option>
                <option value="shared">Shared</option>
                <option value="pg">PG</option>
            </select>

            <label for="facilities">Facilities:</label>
            <input type="checkbox" id="wifi" name="facilities" value="Wi-Fi"> Wi-Fi
            <input type="checkbox" id="food" name="facilities" value="Food"> Food
            <input type="checkbox" id="ac" name="facilities" value="AC"> AC
            <input type="checkbox" id="gym" name="facilities" value="Gym"> Gym

            <button type="submit">Update Hostel</button>
        </form>
    </section>

    <section id="social-media">
        <h2>Follow Us</h2>
        <a href="https://www.instagram.com/nso_suresh" target="_blank">Instagram</a>
        <a href="https://www.facebook.com" target="_blank">Facebook</a>
        <a href="https://twitter.com" target="_blank">Twitter</a>
    </section>

    <footer>
        <p>© 2025 Find My Hostel (NSO). All rights reserved.</p>
    </footer>

</body>

</html>


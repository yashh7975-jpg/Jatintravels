# Jatintravels
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jatin Tour and Travels</title>
    
    <style>
        /* CSS Styling Shuru */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #121212; /* Dark theme background */
            color: #ffffff;
            display: flex; /* Flexbox for alignment */
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }
        
        header {
            width: 100%;
            background-color: #1a1a1a;
            padding: 20px;
            text-align: center;
            border-bottom: 3px solid #e74c3c;
        }
        
        header h1 {
            margin-bottom: 5px;
            letter-spacing: 1px;
            font-size: 1.8rem;
        }
        
        header p {
            color: #bdc3c7;
            font-size: 0.95rem;
        }
        
        .container {
            width: 90%;
            max-width: 450px;
            background-color: #1e272e;
            margin: 30px auto;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.5);
        }
        
        .info-banner {
            background-color: #e74c3c;
            color: white;
            padding: 12px;
            text-align: center;
            border-radius: 6px;
            margin-bottom: 25px;
            font-weight: bold;
            font-size: 0.9rem;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
            margin-bottom: 18px;
        }
        
        label {
            margin-bottom: 6px;
            font-size: 0.9rem;
            color: #dfe4ea;
            font-weight: 500;
        }
        
        input, select {
            padding: 12px;
            border: 1px solid #4a4a4a;
            border-radius: 6px;
            background-color: #2f3640;
            color: #ffffff;
            font-size: 1rem;
            outline: none;
            transition: border-color 0.3s;
        }
        
        input:focus, select:focus {
            border-color: #e74c3c;
        }
        
        /* Placeholder ko color dene ka code */
        ::placeholder {
            color: #7f8fa6;
            opacity: 1;
        }
        
        .submit-btn {
            width: 100%;
            background-color: #2ed573;
            color: #121212;
            padding: 15px;
            border: none;
            border-radius: 6px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            margin-top: 15px;
            transition: background-color 0.3s, transform 0.1s;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }
        
        .submit-btn:hover {
            background-color: #27ae60;
        }
        
        .submit-btn:active {
            transform: scale(0.98);
        }
    </style>
</head>
<body>

    <!-- Main Content -->
    <header>
        <h1>Jatin Tour and Travels</h1>
        <p>Premium Car Rental Services</p>
    </header>

    <div class="container">
        <!-- Strictly Cars Only Banner -->
        <div class="info-banner">
            ⚠️ Only Car Rentals Available<br>
            <span style="font-size: 0.8rem; font-weight: normal;">(We do not provide Hotel & Meal packages)</span>
        </div>

        <form id="bookingForm">
            <div class="form-group">
                <label for="name">Aapka Naam</label>
                <input type="text" id="name" placeholder="e.g. Chirag" required>
            </div>
            
            <div class="form-group">
                <label for="phone">Phone Number</label>
                <input type="tel" id="phone" placeholder="10-digit mobile number" required pattern="[0-9]{10}">
            </div>

            <div class="form-group">
                <label for="car">Gaadi Select Karein</label>
                <select id="car" required>
                    <option value="" disabled selected>Gaadi select karein</option>
                    <option value="Mahindra Scorpio S11">Mahindra Scorpio S11 (Classic)</option>
                    <option value="Maruti Baleno">Maruti Baleno (HR10AW1351)</option>
                    <option value="Toyota Innova Crysta">Toyota Innova Crysta</option>
                    <option value="Maruti Ertiga">Maruti Ertiga</option>
                    <option value="Swift Dzire">Maruti Swift Dzire</option>
                </select>
            </div>

            <div class="form-group">
                <label for="pickup">Pickup Location</label>
                <input type="text" id="pickup" placeholder="Kahan se gaadi leni hai?" required>
            </div>

            <div class="form-group">
                <label for="days">Kitne Din Ke Liye?</label>
                <input type="number" id="days" placeholder="Number of days" required min="1">
            </div>

            <button type="submit" class="submit-btn">
                WhatsApp Par Book Karein 🟢
            </button>
        </form>
    </div>

    <!-- JavaScript (Form Submit Hote hi WhatsApp Kholne ke liye) -->
    <script>
        document.getElementById('bookingForm').addEventListener('submit', function(e) {
            e.preventDefault(); // Page ko refresh hone se rokega
            
            // User jo form mein likhega usko yahan save kar rahe hain
            let name = document.getElementById('name').value;
            let phone = document.getElementById('phone').value;
            let car = document.getElementById('car').value;
            let pickup = document.getElementById('pickup').value;
            let days = document.getElementById('days').value;
            
            // Jatin bhai ka WhatsApp Number (India ke +91 ke sath)
            let waNumber = "919910912129"; 
            
            // WhatsApp par jo message bhejenge uska design
            let message = `*New Booking Enquiry - Jatin Tour & Travels*%0A%0A`;
            message += `*Name:* ${name}%0A`;
            message += `*Contact:* ${phone}%0A`;
            message += `*Car Selected:* ${car}%0A`;
            message += `*Pickup Location:* ${pickup}%0A`;
            message += `*Duration:* ${days} Days%0A%0A`;
            message += `_Note: Customer only needs transport (No Hotels/Meals)._`;
            
            // WhatsApp ka link banakar naye tab mein kholna
            let waLink = `https://wa.me/${waNumber}?text=${message}`;
            window.open(waLink, '_blank');
        });
    </script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Book Your Palawan Vacation</title>
    <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-image: url('https://mindfulnessmemories.com/wp-content/uploads/2021/05/el-nido-palawan-aerial-drone-view-of-tropical-entalula-island-huge-steep-rocks-cliffs-mountains.jpg');
            background-color: #2E8B57; 
            color: white;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .container {
            width: 90%;
            max-width: 600px;
            background: rgba(0, 0, 0, 0.7);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
        }
        h1 {
            margin-bottom: 20px;
        }
        label {
            display: block;
            font-size: 18px;
            margin-top: 10px;
        }
        select, input {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: none;
            border-radius: 5px;
        }
        button {
            background-color: #ff7f50;
            color: white;
            font-size: 18px;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            margin-top: 15px;
            cursor: pointer;
            transition: 0.3s;
            width: 100%;
        }
        button:hover {
            background-color: #e65c00;
        }
        #confirmation {
            font-size: 20px;
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>🌴 Book Your Dream Vacation in Palawan 🌊</h1>

        <label for="package">Choose a Travel Package:</label>
        <select id="package">
            <option value="15000">El Nido - ₱15,000 (Kayaking, Snorkeling)</option>
            <option value="12000">Coron - ₱12,000 (Scuba Diving, Island Hopping)</option>
            <option value="10000">Puerto Princesa - ₱10,000 (Underground River Tour, Island Hopping)</option>
        </select>

        <label for="accommodation">Accommodation Type:</label>
        <select id="accommodation">
            <option value="3000">Budget Hotel - ₱3,000</option>
            <option value="5000">Resort - ₱5,000</option>
            <option value="10000">Luxury Villa - ₱10,000</option>
        </select>

        <label for="days">Vacation_Days:</label>
        <input type="number" id="days" placeholder="Enter number of days" required min="1">

        <label for="name">Full Name:</label>
        <input type="text" id="name" placeholder="Enter your full name" required>

        <label for="email">Email Address:</label>
        <input type="email" id="email" placeholder="Enter your email" required>

        <label for="date">Select Travel Date:</label>
        <input type="date" id="date" required>

        <button onclick="bookVacation()">Book Now</button>

        <p id="confirmation"></p>
    </div>

    <script>
        (function() {
            emailjs.init("YOUR_PUBLIC_KEY"); // Replace with your EmailJS Public Key
        })();

        function bookVacation() {
            let packagePrice = parseInt(document.getElementById("package").value);
            let accommodationPrice = parseInt(document.getElementById("accommodation").value);
            let days = parseInt(document.getElementById("days").value);
            let name = document.getElementById("name").value;
            let email = document.getElementById("email").value;
            let date = document.getElementById("date").value;

            if (!name || !email || !date || !days || days <= 0) {
                document.getElementById("confirmation").innerText = "❌ Please fill out all fields correctly!";
                return;
            }

            let totalCost = (packagePrice + accommodationPrice) * days;

            let message = `✅ Thank you, ${name}! Your Palawan vacation has been booked for ${date} for ${days} days. 
            \nPackage Cost: ₱${packagePrice}
            \nAccommodation Cost: ₱${accommodationPrice}
            \nTotal Cost: ₱${totalCost}
            \nA confirmation email has been sent to ${email}.`;

            document.getElementById("confirmation").innerText = message;

            // Send email using EmailJS
            let templateParams = {
                to_email: email,
                from_name: "Palawan Travel Agency",
                user_name: name,
                booking_date: date,
                package_selected: `₱${packagePrice}`,
                accommodation_selected: `₱${accommodationPrice}`,
                total_cost: `₱${totalCost}`,
                vacation_days: days
            };

            emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", templateParams)
                .then(response => {
                    console.log("Email sent successfully!", response);
                }, error => {
                    console.log("Failed to send email", error);
                });
        }
    </script>

</body>
</html>

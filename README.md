# refer-and-earn-frontend 
In this i gave html,css,java script codes
index.html code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Refer & Earn</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <!-- Header -->
    <header>
        <h1>Accredian</h1>
        <nav>
            <ul>
                <li><a href="#">Refer</a></li>
                <li><a href="#">Benefits</a></li>
                <li><a href="#">FAQs</a></li>
                <li><a href="#">Support</a></li>
                <li><a href="#">Your Referrals</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h2>Let's Learn & Earn</h2>
        <p>Get a chance to win up to <strong>Rs. 15,000</strong></p>
        <a href="#" class="btn">Refer Now</a>
    </section>

    <!-- How It Works -->
    <section class="how-it-works">
        <h2>How Do I Refer?</h2>
        <div class="steps">
            <div class="step">
                <h3>Invite Friends</h3>
                <p>Share your referral link with friends.</p>
            </div>
            <div class="step">
                <h3>Friends Enroll</h3>
                <p>Your friends enroll in the program.</p>
            </div>
            <div class="step">
                <h3>Earn Rewards</h3>
                <p>Receive exciting rewards for referrals.</p>
            </div>
        </div>
        <a href="#" class="btn">Refer Now</a>
    </section>

    <!-- Referral Benefits Table -->
    <section class="benefits">
        <h2>What Are The Referral Benefits?</h2>
        <div class="table-container">
            <table>
                <tr>
                    <th>Program</th>
                    <th>Referrer Bonus</th>
                    <th>Referee Bonus</th>
                </tr>
                <tr>
                    <td>Professional Certification in Product Management</td>
                    <td>₹15,000</td>
                    <td>₹12,000</td>
                </tr>
                <tr>
                    <td>PG Certificate Program in Strategic Product Management</td>
                    <td>₹10,000</td>
                    <td>₹8,000</td>
                </tr>
            </table>
        </div>
        <a href="#" class="btn">Refer Now</a>
    </section>

    <!-- Referral Link Generator -->
    <section class="referral-generator">
        <h2>Generate Your Referral Link</h2>
        <input type="text" id="referralLink" readonly placeholder="Your referral link will appear here">
        <button onclick="generateReferralLink()">Generate Link</button>
        <button onclick="copyLink()">Copy Link</button>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 Accredian. All rights reserved.</p>
    </footer>

    <script src="script1.js"></script>
</body>
</html>
styles.css code
/* General Styles */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    text-align: center;
}

/* Header */
header {
    background: #007bff;
    color: white;
    padding: 15px 0;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

/* Hero Section */
.hero {
    background: #f0f8ff;
    padding: 50px 20px;
}

.btn {
    display: inline-block;
    background: #007bff;
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    margin-top: 10px;
    border-radius: 5px;
}

/* Steps */
.steps {
    display: flex;
    justify-content: center;
    gap: 30px;
}

.step {
    background: #f9f9f9;
    padding: 20px;
    width: 200px;
    border-radius: 10px;
}

/* Benefits Table */
.table-container {
    width: 80%;
    margin: auto;
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin: 20px 0;
}

th, td {
    border: 1px solid #ddd;
    padding: 10px;
    text-align: left;
}

th {
    background: #007bff;
    color: white;
}

/* Referral Generator */
.referral-generator {
    margin: 20px 0;
}

input {
    width: 60%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px 15px;
    border: none;
    background: #007bff;
    color: white;
    cursor: pointer;
    border-radius: 5px;
}

button:hover {
    background: #0056b3;
}

/* Footer */
footer {
    background: #333;
    color: white;
    padding: 10px 0;
    margin-top: 20px;
}
script.js
document.addEventListener("DOMContentLoaded", function () {
    const generateBtn = document.getElementById("generateLink");
    const copyBtn = document.getElementById("copyLink");
    const referralInput = document.getElementById("referralLink");

    if (!generateBtn || !copyBtn || !referralInput) {
        console.error("Buttons or input field not found! Check HTML IDs.");
        return;
    }

    function generateReferralLink() {
        const referralCode = Math.random().toString(36).substring(2, 10);
        const referralLink = https://example.com/referral?code=${referralCode};
        referralInput.value = referralLink;
    }

    function copyReferralLink() {
        if (referralInput.value === "") {
            alert("Please generate a referral link first!");
            return;
        }
        navigator.clipboard.writeText(referralInput.value)
            .then(() => alert("Referral link copied to clipboard!"))
            .catch(() => alert("Failed to copy!"));
    }

    generateBtn.addEventListener("click", generateReferralLink);
    copyBtn.addEventListener("click", copyReferralLink);
});

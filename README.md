# Weedingcardmaker
Here you can make wedding cards for free
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wedding Card Maker - Create Beautiful Invitations</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        :root {
            --primary: #d4af37;
            --secondary: #8b4513;
            --accent: #c19b2a;
            --light: #f9f7f2;
            --dark: #333;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        body {
            background-color: #f5f5f5;
            color: var(--dark);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: white;
            color: var(--dark);
            padding: 15px 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            font-size: 2rem;
            color: var(--primary);
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--secondary);
        }

        .nav-links {
            display: flex;
            gap: 25px;
        }

        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .language-selector {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .language-selector select {
            padding: 8px 15px;
            border-radius: 5px;
            border: 1px solid #ddd;
            background: white;
            color: var(--dark);
            font-weight: 500;
            cursor: pointer;
        }

        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 80px 0;
            text-align: center;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 20px;
            font-weight: 700;
        }

        .section-title {
            text-align: center;
            margin: 60px 0 40px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--secondary);
            display: inline-block;
            padding-bottom: 10px;
        }

        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background: var(--primary);
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }

        .templates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .template-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            position: relative;
        }

        .template-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .template-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--primary);
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 2;
        }

        .template-img {
            height: 200px;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            font-weight: 600;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        /* Template Backgrounds - EXACTLY like before */
        .royal-gold-bg {
            background: 
                linear-gradient(135deg, #d4af37 0%, #f7ef8a 50%, #b8860b 100%),
                repeating-linear-gradient(45deg, transparent, transparent 10px, rgba(255,255,255,0.1) 10px, rgba(255,255,255,0.1) 20px);
        }

        .divine-red-bg {
            background: 
                linear-gradient(135deg, #dc2626 0%, #f87171 50%, #b91c1c 100%),
                radial-gradient(circle at 20% 80%, rgba(255,255,255,0.2) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255,255,255,0.2) 0%, transparent 50%);
        }

        .sacred-purple-bg {
            background: 
                linear-gradient(135deg, #7c3aed 0%, #a78bfa 50%, #5b21b6 100%),
                repeating-radial-gradient(circle at 50% 50%, transparent, transparent 10px, rgba(255,255,255,0.1) 10px, rgba(255,255,255,0.1) 20px);
        }

        .floral-pink-bg {
            background: 
                linear-gradient(135deg, #ec4899 0%, #f9a8d4 50%, #db2777 100%),
                linear-gradient(45deg, transparent 49%, rgba(255,255,255,0.1) 49%, rgba(255,255,255,0.1) 51%, transparent 51%),
                linear-gradient(-45deg, transparent 49%, rgba(255,255,255,0.1) 49%, rgba(255,255,255,0.1) 51%, transparent 51%);
        }

        .marathi-orange-bg {
            background: 
                linear-gradient(135deg, #ea580c 0%, #fdba74 50%, #c2410c 100%),
                radial-gradient(ellipse at center, rgba(255,255,255,0.2) 0%, transparent 70%);
        }

        .luxury-gold-bg {
            background: 
                linear-gradient(135deg, #000000 0%, #434343 50%, #000000 100%),
                repeating-linear-gradient(90deg, transparent, transparent 5px, rgba(212,175,55,0.3) 5px, rgba(212,175,55,0.3) 10px);
        }

        .template-info {
            padding: 20px;
            background: white;
        }

        .template-info h3 {
            margin-bottom: 10px;
            color: var(--secondary);
        }

        .template-info p {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .use-template {
            display: block;
            width: 100%;
            padding: 12px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .use-template:hover {
            background: var(--accent);
            transform: translateY(-2px);
        }

        .customizer {
            background: white;
            padding: 60px 0;
            margin: 60px 0;
            box-shadow: var(--shadow);
        }

        .customizer-container {
            display: flex;
            gap: 40px;
            flex-wrap: wrap;
        }

        .customizer-form {
            flex: 1;
            min-width: 300px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--secondary);
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .preview-container {
            flex: 1;
            min-width: 300px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .card-preview {
            width: 100%;
            max-width: 500px;
            min-height: 400px;
            border-radius: 15px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
            padding: 40px;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
        }

        .preview-content {
            text-align: center;
            z-index: 2;
            position: relative;
        }

        .preview-title {
            font-family: 'Great Vibes', cursive;
            font-size: 2.8rem;
            margin-bottom: 25px;
        }

        .preview-couple {
            font-size: 2rem;
            margin-bottom: 20px;
            font-family: 'Playfair Display', serif;
        }

        .preview-date, .preview-venue {
            margin-bottom: 12px;
            font-size: 1.1rem;
        }

        .preview-message {
            font-style: italic;
            margin: 25px 0;
            line-height: 1.8;
        }

        .action-buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-primary:hover {
            background: var(--accent);
        }

        .btn-secondary {
            background: #6c757d;
            color: white;
        }

        .btn-secondary:hover {
            background: #5a6268;
        }

        footer {
            background: var(--secondary);
            color: white;
            padding: 60px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-column h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-column h3:after {
            content: '';
            position: absolute;
            width: 40px;
            height: 2px;
            background: var(--primary);
            bottom: 0;
            left: 0;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #ddd;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--primary);
            padding-left: 5px;
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: #aaa;
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }

            .nav-links {
                gap: 15px;
            }

            .customizer-container {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-heart"></i>
                    <h1>Wedding Card Maker</h1>
                </div>
                <div class="nav-links">
                    <a href="#">Home</a>
                    <a href="#">Templates</a>
                    <a href="#">Languages</a>
                    <a href="#">Pricing</a>
                    <a href="#">Contact</a>
                </div>
                <div class="language-selector">
                    <i class="fas fa-globe"></i>
                    <select id="siteLanguage">
                        <option value="en">English</option>
                        <option value="hi">Hindi</option>
                        <option value="mr">Marathi</option>
                        <option value="ta">Tamil</option>
                        <option value="te">Telugu</option>
                    </select>
                </div>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h2>Create Beautiful Wedding Cards</h2>
            <p>Choose from our exclusive collection of colorful designed templates</p>
            <a href="#customizer" class="cta-button" style="display: inline-block; background: white; color: var(--secondary); padding: 15px 40px; border-radius: 50px; text-decoration: none; font-weight: 600; margin-top: 20px;">Start Creating Now</a>
        </div>
    </section>

    <section class="container">
        <div class="section-title">
            <h2>Colorful Template Collection</h2>
        </div>
        
        <div class="templates-grid">
            <!-- Royal Gold Template -->
            <div class="template-card">
                <div class="template-badge">Premium</div>
                <div class="template-img royal-gold-bg">
                    Royal Gold Elegance
                </div>
                <div class="template-info">
                    <h3>Royal Gold</h3>
                    <p>Luxurious golden design with traditional motifs</p>
                    <button class="use-template" data-template="royal-gold">Use This Template</button>
                </div>
            </div>

            <!-- Divine Red Template -->
            <div class="template-card">
                <div class="template-badge">Divine</div>
                <div class="template-img divine-red-bg">
                    Divine Red Blessings
                </div>
                <div class="template-info">
                    <h3>Divine Red</h3>
                    <p>Traditional red design with gods blessings</p>
                    <button class="use-template" data-template="divine-red">Use This Template</button>
                </div>
            </div>

            <!-- Sacred Purple Template -->
            <div class="template-card">
                <div class="template-badge">Sacred</div>
                <div class="template-img sacred-purple-bg">
                    Sacred Purple
                </div>
                <div class="template-info">
                    <h3>Sacred Purple</h3>
                    <p>Spiritual purple design with divine patterns</p>
                    <button class="use-template" data-template="sacred-purple">Use This Template</button>
                </div>
            </div>

            <!-- Floral Pink Template -->
            <div class="template-card">
                <div class="template-badge">Romantic</div>
                <div class="template-img floral-pink-bg">
                    Floral Pink Bliss
                </div>
                <div class="template-info">
                    <h3>Floral Pink</h3>
                    <p>Romantic pink design with beautiful patterns</p>
                    <button class="use-template" data-template="floral-pink">Use This Template</button>
                </div>
            </div>

            <!-- Marathi Orange Template -->
            <div class="template-card">
                <div class="template-badge">Traditional</div>
                <div class="template-img marathi-orange-bg">
                    Marathi Traditional
                </div>
                <div class="template-info">
                    <h3>Marathi Traditional</h3>
                    <p>Authentic Marathi design with cultural elements</p>
                    <button class="use-template" data-template="marathi-orange">Use This Template</button>
                </div>
            </div>

            <!-- Luxury Gold Template -->
            <div class="template-card">
                <div class="template-badge">Luxury</div>
                <div class="template-img luxury-gold-bg">
                    Luxury Gold
                </div>
                <div class="template-info">
                    <h3>Luxury Gold</h3>
                    <p>Premium black and gold sophisticated design</p>
                    <button class="use-template" data-template="luxury-gold">Use This Template</button>
                </div>
            </div>
        </div>
    </section>

    <section class="customizer" id="customizer">
        <div class="container">
            <div class="section-title">
                <h2>Customize Your Wedding Card</h2>
            </div>
            
            <div class="customizer-container">
                <div class="customizer-form">
                    <div class="form-group">
                        <label for="groomName">Groom's Name</label>
                        <input type="text" id="groomName" placeholder="Enter groom's name">
                    </div>
                    
                    <div class="form-group">
                        <label for="brideName">Bride's Name</label>
                        <input type="text" id="brideName" placeholder="Enter bride's name">
                    </div>
                    
                    <div class="form-group">
                        <label for="weddingDate">Wedding Date</label>
                        <input type="date" id="weddingDate">
                    </div>
                    
                    <div class="form-group">
                        <label for="weddingTime">Wedding Time</label>
                        <input type="time" id="weddingTime">
                    </div>
                    
                    <div class="form-group">
                        <label for="weddingVenue">Wedding Venue</label>
                        <input type="text" id="weddingVenue" placeholder="Enter wedding venue">
                    </div>
                    
                    <div class="form-group">
                        <label for="cardLanguage">Card Language</label>
                        <select id="cardLanguage">
                            <option value="en">English</option>
                            <option value="hi">Hindi</option>
                            <option value="mr">Marathi</option>
                            <option value="ta">Tamil</option>
                            <option value="te">Telugu</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="personalMessage">Personal Message</label>
                        <textarea id="personalMessage" placeholder="Enter your personal message"></textarea>
                    </div>
                    
                    <button class="btn btn-primary" id="updatePreview">Update Preview</button>
                </div>
                
                <div class="preview-container">
                    <div class="card-preview royal-gold-bg" id="cardPreview">
                        <div class="preview-content">
                            <h3 class="preview-title" id="previewTitle">Wedding Invitation</h3>
                            <div class="preview-couple" id="previewCouple">John & Jane</div>
                            <div class="preview-date" id="previewDate">Saturday, June 15, 2024</div>
                            <div class="preview-date" id="previewTime">4:00 PM</div>
                            <div class="preview-venue" id="previewVenue">Grand Ballroom, City Hotel</div>
                            <p class="preview-message" id="previewMessage">
                                With joy in our hearts, we invite you to celebrate our special day as we exchange vows and begin our journey together as husband and wife.
                            </p>
                        </div>
                    </div>
                    
                    <div class="action-buttons">
                        <button class="btn btn-primary" id="downloadCard">Download Card</button>
                        <button class="btn btn-secondary" id="shareCard">Share Card</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Wedding Card Maker</h3>
                    <p>Creating beautiful wedding invitations for couples across India and beyond.</p>
                </div>
                
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Templates</a></li>
                        <li><a href="#">Languages</a></li>
                        <li><a href="#">Pricing</a></li>
                        <li><a href="#">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Languages</h3>
                    <ul class="footer-links">
                        <li><a href="#">English</a></li>
                        <li><a href="#">Hindi</a></li>
                        <li><a href="#">Marathi</a></li>
                        <li><a href="#">Tamil</a></li>
                        <li><a href="#">Telugu</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <ul class="footer-links">
                        <li><a href="#"><i class="fas fa-envelope"></i> info@weddingcardmaker.com</a></li>
                        <li><a href="#"><i class="fas fa-phone"></i> +91 98765 43210</a></li>
                        <li><a href="#"><i class="fas fa-map-marker-alt"></i> Mumbai, India</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2024 Wedding Card Maker. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Language-specific content
        const languageContent = {
            en: {
                title: "Wedding Invitation",
                couple: "John & Jane",
                date: "Saturday, June 15, 2024",
                time: "4:00 PM",
                venue: "Grand Ballroom, City Hotel",
                message: "With joy in our hearts, we invite you to celebrate our special day as we exchange vows and begin our journey together as husband and wife."
            },
            hi: {
                title: "शादी का निमंत्रण",
                couple: "राहुल & प्रिया",
                date: "शनिवार, 15 जून, 2024",
                time: "शाम 4:00 बजे",
                venue: "ग्रैंड बॉलरूम, सिटी होटल",
                message: "हमारे दिलों में खुशी के साथ, हम आपको हमारे विशेष दिन का जश्न मनाने के लिए आमंत्रित करते हैं क्योंकि हम वचनों का आदान-प्रदान करते हैं और पति और पत्नी के रूप में एक साथ अपनी यात्रा शुरू करते हैं।"
            },
            mr: {
                title: "लग्नाचे निमंत्रण",
                couple: "राज & सोनाली",
                date: "शनिवार, 15 जून, 2024",
                time: "संध्याकाळी 4:00 वाजता",
                venue: "ग्रँड बॉलरूम, सिटी हॉटेल",
                message: "आमच्या हृदयात आनंद असताना, आम्ही तुम्हाला आमच्या विशेष दिवसाचा साजरा करण्यासाठी आमंत्रित करतो कारण आम्ही शपथा घेतो आणि पती आणि पत्नी म्हणून एकत्र प्रवास सुरू करतो।"
            },
            ta: {
                title: "திருமண அழைப்பிதழ்",
                couple: "அரவிந்த் & பிரியா",
                date: "சனி, ஜூன் 15, 2024",
                time: "மாலை 4:00 மணி",
                venue: "கிராண்ட் பால்ரூம், சிட்டி ஹோட்டல்",
                message: "எங்கள் இதயங்களில் மகிழ்ச்சியுடன், எங்கள் சிறப்பு நாளைக் கொண்டாட உங்களை அழைக்கிறோம், ஏனெனில் நாங்கள் சபதங்களை பரிமாறிக் கொண்டு கணவன் மற்றும் மனைவியாக ஒன்றாக எங்கள் பயணத்தைத் தொடங்குகிறோம்."
            },
            te: {
                title: "వివాహ ఆహ్వానం",
                couple: "రాజ్ & ప్రియా",
                date: "శనివారం, జూన్ 15, 2024",
                time: "సాయంత్రం 4:00 గంటలు",
                venue: "గ్రాండ్ బాల్రూమ్, సిటీ హోటల్",
                message: "మా హృదయాల్లో ఆనందంతో, మేము ప్రతిజ్ఞలను మార్పుచేసుకుని భర్త మరియు భార్యగా కలిసి మా ప్రయాణాన్ని ప్రారంభించేటప్పుడు మా ప్రత్యేక రోజును జరుపుకోవడానికి మేము మిమ్మల్ని ఆహ్వానిస్తున్నాము."
            }
        };

        document.addEventListener('DOMContentLoaded', function() {
            const nextMonth = new Date();
            nextMonth.setMonth(nextMonth.getMonth() + 1);
            document.getElementById('weddingDate').valueAsDate = nextMonth;
            
            document.getElementById('weddingTime').value = "16:00";

            const templateButtons = document.querySelectorAll('.use-template');
            templateButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const template = this.getAttribute('data-template');
                    applyTemplate(template);
                });
            });

            document.getElementById('cardLanguage').addEventListener('change', function() {
                updatePreview();
            });

            document.getElementById('siteLanguage').addEventListener('change', function() {
                document.getElementById('cardLanguage').value = this.value;
                updatePreview();
            });

            document.getElementById('updatePreview').addEventListener('click', updatePreview);

            document.getElementById('downloadCard').addEventListener('click', function() {
                alert('Your wedding card would be downloaded!');
            });

            document.getElementById('shareCard').addEventListener('click', function() {
                alert('Share your beautiful wedding card!');
            });

            function applyTemplate(template) {
                const cardPreview = document.getElementById('cardPreview');
                cardPreview.className = 'card-preview';
                cardPreview.classList.add(template + '-bg');
                updatePreview();
            }

            function updatePreview() {
                const groomName = document.getElementById('groomName').value || 'John';
                const brideName = document.getElementById('brideName').value || 'Jane';
                const weddingDate = document.getElementById('weddingDate').valueAsDate;
                const weddingTime = document.getElementById('weddingTime').value;
                const weddingVenue = document.getElementById('weddingVenue').value || 'Grand Ballroom, City Hotel';
                const language = document.getElementById('cardLanguage').value;
                const message = document.getElementById('personalMessage').value || languageContent[language].message;
                
                const content = languageContent[language] || languageContent.en;
                
                let formattedDate = content.date;
                if (weddingDate) {
                    const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
                    formattedDate = weddingDate.toLocaleDateString(getLocale(language), options);
                }
                
                let formattedTime = content.time;
                if (weddingTime) {
                    const [hours, minutes] = weddingTime.split(':');
                    const hour = parseInt(hours);
                    const ampm = hour >= 12 ? 'PM' : 'AM';
                    const displayHour = hour % 12 || 12;
                    formattedTime = `${displayHour}:${minutes} ${ampm}`;
                }
                
                document.getElementById('previewTitle').textContent = content.title;
                document.getElementById('previewCouple').textContent = `${groomName} & ${brideName}`;
                document.getElementById('previewDate').textContent = formattedDate;
                document.getElementById('previewTime').textContent = formattedTime;
                document.getElementById('previewVenue').textContent = weddingVenue;
                document.getElementById('previewMessage').textContent = message;
            }

            function getLocale(language) {
                const locales = {
                    'en': 'en-US',
                    'hi': 'hi-IN',
                    'mr': 'mr-IN',
                    'ta': 'ta-IN',
                    'te': 'te-IN'
                };
                return locales[language] || 'en-US';
            }

            updatePreview();
        });
    </script>
</body>
</html>

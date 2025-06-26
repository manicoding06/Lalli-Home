<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lallihome - Premium Real Estate Properties</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: #fff;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #e74c3c;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #e74c3c;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23f8f9fa" width="1200" height="600"/><text x="600" y="300" text-anchor="middle" fill="%23666" font-size="24">Luxury Property Background</text></svg>');
            height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: white;
            background-size: cover;
            background-position: center;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.3s both;
        }

        .cta-button {
            display: inline-block;
            background: #e74c3c;
            color: white;
            padding: 15px 30px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: all 0.3s;
            animation: fadeInUp 1s ease 0.6s both;
        }

        .cta-button:hover {
            background: #c0392b;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(231, 76, 60, 0.4);
        }

        /* Properties Section */
        .properties {
            padding: 80px 0;
            background: #f8f9fa;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
        }

        .properties-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .property-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s;
            cursor: pointer;
        }

        .property-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .property-image {
            height: 250px;
            background: linear-gradient(45deg, #ddd, #eee);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #666;
            font-size: 1.1rem;
            position: relative;
            overflow: hidden;
        }

        .property-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            opacity: 0.1;
        }

        .property-info {
            padding: 1.5rem;
        }

        .property-price {
            font-size: 1.8rem;
            font-weight: bold;
            color: #e74c3c;
            margin-bottom: 0.5rem;
        }

        .property-title {
            font-size: 1.3rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #2c3e50;
        }

        .property-location {
            color: #666;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .property-features {
            display: flex;
            gap: 1rem;
            margin-bottom: 1rem;
            font-size: 0.9rem;
            color: #666;
        }

        .feature {
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        .view-details {
            background: #2c3e50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            width: 100%;
        }

        .view-details:hover {
            background: #34495e;
        }

        /* About Section */
        .about {
            padding: 80px 0;
            background: white;
        }

        .about-content {
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .about-content p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            color: #666;
        }

        /* Contact Section */
        .contact {
            padding: 80px 0;
            background: #2c3e50;
            color: white;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .contact-info h3 {
            margin-bottom: 1rem;
            color: #e74c3c;
        }

        .contact-form {
            display: grid;
            gap: 1rem;
        }

        .contact-form input,
        .contact-form textarea {
            padding: 12px;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
        }

        .contact-form button {
            background: #e74c3c;
            color: white;
            padding: 15px;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: background 0.3s;
        }

        .contact-form button:hover {
            background: #c0392b;
        }

        /* Footer */
        footer {
            background: #1a252f;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Property Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.8);
        }

        .modal-content {
            background-color: white;
            margin: 5% auto;
            padding: 2rem;
            border-radius: 10px;
            width: 90%;
            max-width: 600px;
            position: relative;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            position: absolute;
            right: 20px;
            top: 15px;
        }

        .close:hover {
            color: #000;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .contact-content {
                grid-template-columns: 1fr;
            }
            
            .properties-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <a href="#" class="logo">Lallihome</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#properties">Properties</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Discover Your Dream Home</h1>
                <p>Premium real estate properties curated for discerning buyers</p>
                <a href="#properties" class="cta-button">View Properties</a>
            </div>
        </div>
    </section>

    <!-- Properties Section -->
    <section id="properties" class="properties">
        <div class="container">
            <h2 class="section-title">Featured Properties</h2>
            <div class="properties-grid">
                <!-- Property 1 -->
                <div class="property-card" onclick="openModal('property1')">
                    <div class="property-image">
                        <span>Luxury Villa Image</span>
                    </div>
                    <div class="property-info">
                        <div class="property-price">$1,250,000</div>
                        <div class="property-title">Modern Luxury Villa</div>
                        <div class="property-location">
                            <span>📍</span> Beverly Hills, CA
                        </div>
                        <div class="property-features">
                            <div class="feature">🛏️ 4 Beds</div>
                            <div class="feature">🛁 3 Baths</div>
                            <div class="feature">📐 3,200 sq ft</div>
                        </div>
                        <button class="view-details">View Details</button>
                    </div>
                </div>

                <!-- Property 2 -->
                <div class="property-card" onclick="openModal('property2')">
                    <div class="property-image">
                        <span>Downtown Penthouse Image</span>
                    </div>
                    <div class="property-info">
                        <div class="property-price">$950,000</div>
                        <div class="property-title">Downtown Penthouse</div>
                        <div class="property-location">
                            <span>📍</span> Manhattan, NY
                        </div>
                        <div class="property-features">
                            <div class="feature">🛏️ 3 Beds</div>
                            <div class="feature">🛁 2 Baths</div>
                            <div class="feature">📐 2,100 sq ft</div>
                        </div>
                        <button class="view-details">View Details</button>
                    </div>
                </div>

                <!-- Property 3 -->
                <div class="property-card" onclick="openModal('property3')">
                    <div class="property-image">
                        <span>Waterfront Estate Image</span>
                    </div>
                    <div class="property-info">
                        <div class="property-price">$2,100,000</div>
                        <div class="property-title">Waterfront Estate</div>
                        <div class="property-location">
                            <span>📍</span> Malibu, CA
                        </div>
                        <div class="property-features">
                            <div class="feature">🛏️ 5 Beds</div>
                            <div class="feature">🛁 4 Baths</div>
                            <div class="feature">📐 4,500 sq ft</div>
                        </div>
                        <button class="view-details">View Details</button>
                    </div>
                </div>

                <!-- Property 4 -->
                <div class="property-card" onclick="openModal('property4')">
                    <div class="property-image">
                        <span>Historic Townhouse Image</span>
                    </div>
                    <div class="property-info">
                        <div class="property-price">$750,000</div>
                        <div class="property-title">Historic Townhouse</div>
                        <div class="property-location">
                            <span>📍</span> Boston, MA
                        </div>
                        <div class="property-features">
                            <div class="feature">🛏️ 3 Beds</div>
                            <div class="feature">🛁 2 Baths</div>
                            <div class="feature">📐 1,800 sq ft</div>
                        </div>
                        <button class="view-details">View Details</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="about-content">
                <h2 class="section-title">Why Choose Lallihome</h2>
                <p>At Lallihome, we specialize in curating exceptional properties that represent the pinnacle of luxury living. Our carefully selected portfolio features only the finest homes in the most desirable locations.</p>
                <p>With years of experience in premium real estate, we understand that buying a home is more than just a transaction—it's about finding the perfect place to create lasting memories.</p>
                <p>Our commitment to excellence and personalized service ensures that every client receives the attention and expertise they deserve throughout their property journey.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <p>📧 info@lallihome.com</p>
                    <p>📞 (555) 123-4567</p>
                    <p>📍 123 Luxury Lane, Premium City, PC 12345</p>
                    <p>🕒 Monday - Friday: 9AM - 6PM<br>Saturday: 10AM - 4PM</p>
                </div>
                <form class="contact-form" onsubmit="handleSubmit(event)">
                    <input type="text" placeholder="Your Name" required>
                    <input type="email" placeholder="Your Email" required>
                    <input type="tel" placeholder="Phone Number">
                    <textarea placeholder="Message" rows="4" required></textarea>
                    <button type="submit">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2025 Lallihome. All rights reserved. | Premium Real Estate Solutions</p>
        </div>
    </footer>

    <!-- Property Modals -->
    <div id="propertyModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <div id="modalContent"></div>
        </div>
    </div>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Property modal functionality
        const propertyDetails = {
            property1: {
                title: "Modern Luxury Villa",
                price: "$1,250,000",
                location: "Beverly Hills, CA",
                description: "Stunning contemporary villa featuring open-concept living, gourmet kitchen with premium appliances, master suite with spa-like bathroom, and beautifully landscaped grounds with pool and entertainment area.",
                features: ["4 Bedrooms", "3 Bathrooms", "3,200 sq ft", "2-car garage", "Swimming pool", "Chef's kitchen", "Walk-in closets", "Smart home technology"]
            },
            property2: {
                title: "Downtown Penthouse",
                price: "$950,000",
                location: "Manhattan, NY",
                description: "Sophisticated penthouse with panoramic city views, floor-to-ceiling windows, modern finishes throughout, and access to building amenities including fitness center and rooftop terrace.",
                features: ["3 Bedrooms", "2 Bathrooms", "2,100 sq ft", "City views", "Modern kitchen", "Hardwood floors", "Building amenities", "Concierge service"]
            },
            property3: {
                title: "Waterfront Estate",
                price: "$2,100,000",
                location: "Malibu, CA",
                description: "Exceptional oceanfront estate with private beach access, expansive outdoor living spaces, infinity pool, and breathtaking sunset views. Perfect for luxury entertaining and coastal living.",
                features: ["5 Bedrooms", "4 Bathrooms", "4,500 sq ft", "Private beach", "Infinity pool", "Ocean views", "Guest house", "Wine cellar"]
            },
            property4: {
                title: "Historic Townhouse",
                price: "$750,000",
                location: "Boston, MA",
                description: "Charming restored townhouse in historic neighborhood, featuring original architectural details, updated amenities, private garden, and walking distance to shops and restaurants.",
                features: ["3 Bedrooms", "2 Bathrooms", "1,800 sq ft", "Historic charm", "Private garden", "Original details", "Updated kitchen", "Prime location"]
            }
        };

        function openModal(propertyId) {
            const property = propertyDetails[propertyId];
            const modalContent = document.getElementById('modalContent');
            
            modalContent.innerHTML = `
                <h2>${property.title}</h2>
                <div style="color: #e74c3c; font-size: 1.5rem; font-weight: bold; margin: 1rem 0;">${property.price}</div>
                <div style="color: #666; margin-bottom: 1rem;">📍 ${property.location}</div>
                <p style="margin-bottom: 1.5rem; line-height: 1.6;">${property.description}</p>
                <h3 style="margin-bottom: 1rem;">Property Features:</h3>
                <ul style="columns: 2; column-gap: 2rem; margin-bottom: 1.5rem;">
                    ${property.features.map(feature => `<li style="margin-bottom: 0.5rem;">${feature}</li>`).join('')}
                </ul>
                <button onclick="contactAboutProperty('${property.title}')" style="background: #e74c3c; color: white; padding: 12px 24px; border: none; border-radius: 5px; cursor: pointer; font-size: 1rem;">Contact About This Property</button>
            `;
            
            document.getElementById('propertyModal').style.display = 'block';
        }

        function closeModal() {
            document.getElementById('propertyModal').style.display = 'none';
        }

        function contactAboutProperty(propertyTitle) {
            const contactSection = document.getElementById('contact');
            closeModal();
            contactSection.scrollIntoView({ behavior: 'smooth' });
            
            // Pre-fill the message
            const messageTextarea = document.querySelector('textarea[placeholder="Message"]');
            messageTextarea.value = `I'm interested in learning more about the ${propertyTitle}. Please contact me with additional details.`;
        }

        function handleSubmit(event) {
            event.preventDefault();
            alert('Thank you for your interest! We will contact you shortly.');
            event.target.reset();
        }

        // Close modal when clicking outside of it
        window.onclick = function(event) {
            const modal = document.getElementById('propertyModal');
            if (event.target === modal) {
                closeModal();
            }
        }
    </script>
</body>
</html>

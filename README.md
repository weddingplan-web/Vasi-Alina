<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Wedding</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            font-family: 'Roboto', sans-serif;
            background-color: #fff8f4;
            color: #333;
        }
        header {
            background: url('https://source.unsplash.com/1600x900/?flowers,roses') no-repeat center/cover;
            height: 100vh;
            color: white;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
        }
        header::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255, 248, 244, 0.9);
            z-index: 1;
        }
        header h1, header p {
            position: relative;
            z-index: 2;
        }
        header h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 4rem;
            margin: 0;
            color: #c97c5d;
        }
        header p {
            font-size: 1.5rem;
            margin: 10px 0;
            color: #4a4a4a;
        }
        #countdown {
            font-size: 1.8rem;
            margin-top: 20px;
            color: #c97c5d;
            font-weight: bold;
        }
        nav {
            background: rgba(255, 255, 255, 0.9);
            display: flex;
            justify-content: center;
            gap: 20px;
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 10px;
            border-bottom: 2px solid #c97c5d;
        }
        nav a {
            text-decoration: none;
            color: #333;
            font-weight: bold;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #c97c5d;
        }
        section {
            padding: 50px 20px;
            text-align: center;
        }
        .our-story, .event-info, .rsvp {
            max-width: 800px;
            margin: 0 auto;
        }
        h2 {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            color: #c97c5d;
            margin-bottom: 20px;
        }
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }
        .gallery img {
            width: 100%;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .rsvp-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        .rsvp-form input, .rsvp-form select, .rsvp-form textarea, .rsvp-form button {
            padding: 10px;
            border: 2px solid #c97c5d;
            border-radius: 5px;
            font-size: 1rem;
        }
        footer {
            background: #c97c5d;
            color: white;
            text-align: center;
            padding: 20px;
        }
    </style>
    <script>
        document.addEventListener("DOMContentLoaded", () => {
            const weddingDate = new Date("April 20, 2025 16:00:00").getTime();

            const countdownInterval = setInterval(() => {
                const now = new Date().getTime();
                const distance = weddingDate - now;

                if (distance < 0) {
                    clearInterval(countdownInterval);
                    document.getElementById("countdown").innerText = "The big day is here!";
                } else {
                    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                    document.getElementById("countdown").innerText = `${days}d ${hours}h ${minutes}m ${seconds}s`;
                }
            }, 1000);
        });
    </script>
</head>
<body>
    <header>
        <h1>Welcome to Our Wedding</h1>
        <p>Join us as we celebrate our love</p>
        <p><strong>April 20, 2025</strong></p>
        <div id="countdown">Loading countdown...</div>
    </header>
    <nav>
        <a href="#our-story">Our Story</a>
        <a href="#the-big-day">The Big Day</a>
        <a href="#gallery">Gallery</a>
        <a href="#rsvp">RSVP</a>
    </nav>
    <section id="our-story" class="our-story">
        <h2>Our Story</h2>
        <p>It all began with a chance meeting, and from there, our journey unfolded into a tale of love, laughter, and endless memories. We can’t wait to start the next chapter with all of you by our side.</p>
    </section>
    <section id="the-big-day" class="event-info">
        <h2>The Big Day</h2>
        <p><strong>Ceremony:</strong> 4:00 PM at Rosewood Gardens</p>
        <p><strong>Reception:</strong> 6:00 PM at Magnolia Hall</p>
        <p><strong>Address:</strong> 123 Wedding Lane, Romance City</p>
    </section>
    <section id="gallery" class="photo-gallery">
        <h2>Gallery</h2>
        <div class="gallery">
            <img src="https://source.unsplash.com/300x300/?engagement" alt="Engagement Photo">
            <img src="https://source.unsplash.com/300x300/?couple" alt="Couple Photo">
            <img src="https://source.unsplash.com/300x300/?wedding" alt="Wedding Decor">
            <img src="https://source.unsplash.com/300x300/?flowers" alt="Flowers">
        </div>
    </section>
    <section id="rsvp" class="rsvp">
        <h2>RSVP</h2>
        <form class="rsvp-form">
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <select>
                <option value="">Will you attend?</option>
                <option value="yes">Yes, with pleasure</option>
                <option value="no">Sorry, I can’t make it</option>
            </select>
            <textarea placeholder="Any dietary restrictions or notes?"></textarea>
            <button type="submit">Submit</button>
        </form>
    </section>
    <footer>
        <p>With Love, [Couple's Names] &copy; 2025</p>
    </footer>
</body>
</html>

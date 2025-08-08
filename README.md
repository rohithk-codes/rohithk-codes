<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rohith - Full Stack Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Inter:wght@300;400;500;600;700&display=swap');
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Inter', sans-serif;
        background: linear-gradient(135deg, #0d1117 0%, #161b22 50%, #21262d 100%);
        color: #e6edf3;
        overflow-x: hidden;
        min-height: 100vh;
    }

    .container {
        max-width: 800px;
        margin: 0 auto;
        padding: 2rem;
        position: relative;
    }

    /* Floating particles background */
    .particles {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        z-index: -1;
    }

    .particle {
        position: absolute;
        width: 4px;
        height: 4px;
        background: #7c3aed;
        border-radius: 50%;
        animation: float 6s ease-in-out infinite;
        opacity: 0.7;
    }

    .particle:nth-child(2) { animation-delay: -1s; background: #06b6d4; }
    .particle:nth-child(3) { animation-delay: -2s; background: #10b981; }
    .particle:nth-child(4) { animation-delay: -3s; background: #f59e0b; }
    .particle:nth-child(5) { animation-delay: -4s; background: #ef4444; }

    @keyframes float {
        0%, 100% { transform: translateY(0) rotate(0deg); opacity: 0.7; }
        50% { transform: translateY(-20px) rotate(180deg); opacity: 1; }
    }

    /* Header section */
    .header {
        text-align: center;
        margin-bottom: 3rem;
        animation: slideInDown 1s ease-out;
    }

    .name {
        font-size: 3.5rem;
        font-weight: 700;
        background: linear-gradient(45deg, #7c3aed, #06b6d4, #10b981);
        background-size: 300% 300%;
        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;
        animation: gradientShift 3s ease-in-out infinite;
        margin-bottom: 1rem;
    }

    .tagline {
        font-size: 1.3rem;
        color: #8b949e;
        margin-bottom: 2rem;
        animation: fadeIn 1s ease-out 0.5s both;
    }

    .typing-text {
        font-family: 'JetBrains Mono', monospace;
        font-size: 1.1rem;
        color: #7c3aed;
        border-right: 2px solid #7c3aed;
        animation: typing 4s steps(40) infinite, blink 1s infinite;
    }

    /* Tech stack */
    .tech-stack {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 1rem;
        margin: 2rem 0;
        animation: slideInUp 1s ease-out 0.8s both;
    }

    .tech-item {
        background: rgba(124, 58, 237, 0.1);
        border: 1px solid rgba(124, 58, 237, 0.3);
        padding: 0.5rem 1rem;
        border-radius: 25px;
        font-size: 0.9rem;
        font-weight: 500;
        transition: all 0.3s ease;
        cursor: pointer;
    }

    .tech-item:hover {
        background: rgba(124, 58, 237, 0.2);
        border-color: #7c3aed;
        transform: translateY(-3px) scale(1.05);
        box-shadow: 0 5px 15px rgba(124, 58, 237, 0.4);
    }

    /* Main content sections */
    .section {
        margin-bottom: 2.5rem;
        padding: 2rem;
        background: rgba(33, 38, 45, 0.5);
        border-radius: 15px;
        border: 1px solid rgba(48, 54, 61, 0.5);
        backdrop-filter: blur(10px);
        animation: fadeInScale 0.8s ease-out;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .section:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    }

    .section-title {
        font-size: 1.5rem;
        font-weight: 600;
        margin-bottom: 1rem;
        color: #f0f6fc;
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }

    .emoji {
        font-size: 1.8rem;
        animation: bounce 2s ease-in-out infinite;
    }

    /* Project showcase */
    .project {
        background: linear-gradient(135deg, rgba(124, 58, 237, 0.1), rgba(6, 182, 212, 0.1));
        padding: 1.5rem;
        border-radius: 10px;
        border: 1px solid rgba(124, 58, 237, 0.2);
        margin-bottom: 1rem;
        transition: all 0.3s ease;
    }

    .project:hover {
        border-color: #7c3aed;
        transform: scale(1.02);
    }

    .project-title {
        font-size: 1.2rem;
        font-weight: 600;
        color: #7c3aed;
        margin-bottom: 0.5rem;
    }

    /* CTA button */
    .cta-button {
        display: inline-block;
        padding: 1rem 2rem;
        background: linear-gradient(45deg, #7c3aed, #06b6d4);
        color: white;
        text-decoration: none;
        border-radius: 50px;
        font-weight: 600;
        font-size: 1.1rem;
        transition: all 0.3s ease;
        animation: pulse 2s ease-in-out infinite;
        box-shadow: 0 4px 15px rgba(124, 58, 237, 0.4);
    }

    .cta-button:hover {
        transform: translateY(-3px) scale(1.05);
        box-shadow: 0 8px 25px rgba(124, 58, 237, 0.6);
        animation: none;
    }

    /* Animations */
    @keyframes gradientShift {
        0%, 100% { background-position: 0% 50%; }
        50% { background-position: 100% 50%; }
    }

    @keyframes typing {
        0%, 50% { width: 0; }
        90%, 100% { width: 100%; }
    }

    @keyframes blink {
        50% { border-color: transparent; }
    }

    @keyframes slideInDown {
        from {
            opacity: 0;
            transform: translateY(-30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes slideInUp {
        from {
            opacity: 0;
            transform: translateY(30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    @keyframes fadeInScale {
        from {
            opacity: 0;
            transform: scale(0.95);
        }
        to {
            opacity: 1;
            transform: scale(1);
        }
    }

    @keyframes bounce {
        0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
        40% { transform: translateY(-10px); }
        60% { transform: translateY(-5px); }
    }

    @keyframes pulse {
        0%, 100% { transform: scale(1); }
        50% { transform: scale(1.05); }
    }

    /* Responsive */
    @media (max-width: 768px) {
        .name { font-size: 2.5rem; }
        .container { padding: 1rem; }
        .section { padding: 1.5rem; }
    }
</style>
</head>
<body>
    <div class="particles">
        <div class="particle" style="left: 10%; top: 20%;"></div>
        <div class="particle" style="left: 80%; top: 30%;"></div>
        <div class="particle" style="left: 60%; top: 70%;"></div>
        <div class="particle" style="left: 20%; top: 80%;"></div>
        <div class="particle" style="left: 90%; top: 10%;"></div>
    </div>
<div class="container">
    <header class="header">
        <h1 class="name">Rohith</h1>
        <p class="tagline">From Marketing Mind to Code Craftsman</p>
        <div class="typing-text">const passion = "building innovative solutions";</div>
    </header>

    <div class="tech-stack">
        <span class="tech-item">JavaScript</span>
        <span class="tech-item">React</span>
        <span class="tech-item">Node.js</span>
        <span class="tech-item">MongoDB</span>
        <span class="tech-item">HTML/CSS</span>
        <span class="tech-item">Bootstrap</span>
    </div>

    <section class="section">
        <h2 class="section-title">
            <span class="emoji">🚀</span>
            My Transformation Journey
        </h2>
        <p>MBA graduate → 2 years marketing → 7 months intensive coding → Full-stack developer ready to innovate! I traded campaigns for commits and discovered my true passion in building digital solutions.</p>
    </section>

    <section class="section">
        <h2 class="section-title">
            <span class="emoji">🏆</span>
            Featured Project
        </h2>
        <div class="project">
            <div class="project-title">🏋️ GYM BUDDY - E-commerce Platform</div>
            <p>Complete MERN stack fitness equipment store with authentication, responsive design, and real-world functionality. Currently building my second project while taking on freelance challenges!</p>
        </div>
    </section>

    <section class="section">
        <h2 class="section-title">
            <span class="emoji">💡</span>
            Why Startups Need Me
        </h2>
        <p><strong>Fresh Perspective:</strong> Marketing background + coding skills = unique problem-solving approach<br>
        <strong>Proven Learner:</strong> Self-taught developer with real project experience<br>
        <strong>Startup Ready:</strong> Thrive in fast-paced, challenging environments where every day brings growth</p>
    </section>

    <section class="section">
        <h2 class="section-title">
            <span class="emoji">🎯</span>
            Ready to Contribute
        </h2>
        <p>Seeking my first IT role in a dynamic startup where I can bring fresh energy, learn from experienced developers, and help build the future. Let's create something amazing together!</p>
        
        <div style="text-align: center; margin-top: 2rem;">
            <a href="mailto:your.email@example.com" class="cta-button">Let's Build Something Great! 🚀</a>
        </div>
    </section>
</div>

<script>
    // Add some interactive particles
    function createParticle() {
        const particle = document.createElement('div');
        particle.className = 'particle';
        particle.style.left = Math.random() * 100 + '%';
        particle.style.top = Math.random() * 100 + '%';
        particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
        document.querySelector('.particles').appendChild(particle);

        setTimeout(() => {
            particle.remove();
        }, 6000);
    }

    // Create particles periodically
    setInterval(createParticle, 2000);

    // Add hover effects to sections
    document.querySelectorAll('.section').forEach((section, index) => {
        section.style.animationDelay = `${index * 0.2}s`;
    });

    // Tech stack hover effects
    document.querySelectorAll('.tech-item').forEach(item => {
        item.addEventListener('mouseenter', function() {
            this.style.animationDuration = '0.5s';
            this.style.animationName = 'pulse';
        });
        
        item.addEventListener('mouseleave', function() {
            this.style.animation = 'none';
        });
    });
</script>
</body>
</html>

[index.html](https://github.com/user-attachments/files/26146782/index.html)
[script.js](https://github.com/user-attachments/files/26146791/script.js)
[style.css](https://github.com/user-attachments/files/26146794/style.css)* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary: #00b894;
  --accent: #e17055;
  --dark: #1a1a1a;
  --light: #f4f6f8;
  --text: #333;
  --white: #fff;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: var(--light);
  color: var(--text);
  line-height: 1.6;
  transition: background 0.3s ease, color 0.3s ease;
}

body.dark-mode {
  --light: #0f0f0f;
  --text: #e0e0e0;
  background: #1a1a1a;
  color: #e0e0e0;
}

/* SCROLL PROGRESS BAR */
.scroll-progress {
  position: fixed;
  top: 0;
  left: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  width: 0%;
  z-index: 999;
  transition: width 0.1s ease;
}

/* NAVBAR */
.navbar {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
  animation: slideDown 0.5s ease-out;
}

body.dark-mode .navbar {
  background: rgba(26, 26, 26, 0.95);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.3);
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 70px;
}

.logo {
  font-size: 1.5em;
  font-weight: bold;
  color: var(--primary);
  letter-spacing: 1px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.logo:hover {
  transform: scale(1.05);
  text-shadow: 0 0 20px rgba(0, 184, 148, 0.5);
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 30px;
}

.nav-link {
  text-decoration: none;
  color: var(--text);
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
  padding: 5px 0;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--accent);
  transition: width 0.3s ease;
}

.nav-link:hover,
.nav-link.active {
  color: var(--accent);
}

.nav-link:hover::after,
.nav-link.active::after {
  width: 100%;
}

.theme-toggle {
  margin-left: 20px;
}

.theme-btn {
  background: none;
  border: none;
  font-size: 1.5em;
  cursor: pointer;
  transition: all 0.3s ease;
  padding: 5px 10px;
}

.theme-btn:hover {
  transform: rotate(20deg) scale(1.1);
}

/* HERO SECTION */
.hero {
  position: relative;
  width: 100%;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  padding: 100px 20px 50px;
}

.background-animation {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  overflow: hidden;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(50px);
  opacity: 0.7;
}

.blob-1 {
  width: 300px;
  height: 300px;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  top: -50px;
  left: -50px;
  animation: float 8s ease-in-out infinite;
}

.blob-2 {
  width: 250px;
  height: 250px;
  background: linear-gradient(135deg, var(--accent), var(--primary));
  bottom: -50px;
  right: -50px;
  animation: float 10s ease-in-out infinite reverse;
}

.blob-3 {
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, #a29bfe, var(--primary));
  top: 50%;
  right: 10%;
  animation: float 12s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translate(0, 0);
  }
  33% {
    transform: translate(30px, -30px);
  }
  66% {
    transform: translate(-20px, 20px);
  }
}

.hero-content {
  position: relative;
  z-index: 2;
  text-align: center;
  animation: fadeInUp 1s ease-out;
}

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

.profile-container {
  margin-bottom: 40px;
}

.profile-image-wrapper {
  position: relative;
  width: 200px;
  height: 200px;
  margin: 0 auto;
  animation: scaleIn 0.8s ease-out;
}

@keyframes scaleIn {
  from {
    opacity: 0;
    transform: scale(0.8);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

.profile-image {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid var(--primary);
  box-shadow: 0 10px 40px rgba(0, 184, 148, 0.3);
  transition: all 0.3s ease;
}

.profile-image:hover {
  transform: scale(1.05);
  box-shadow: 0 15px 50px rgba(0, 184, 148, 0.5);
}

.image-glow {
  position: absolute;
  top: -10px;
  left: -10px;
  right: -10px;
  bottom: -10px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  z-index: -1;
  opacity: 0;
  animation: glow 3s ease-in-out infinite;
}

@keyframes glow {
  0%, 100% {
    opacity: 0;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.1);
  }
}

.hero-title {
  font-size: 4em;
  font-weight: bold;
  margin-bottom: 20px;
  letter-spacing: 2px;
  animation: slideInDown 0.8s ease-out;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
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

.hero-subtitle {
  font-size: 1.5em;
  margin-bottom: 40px;
  animation: slideInUp 0.8s ease-out 0.2s both;
  color: var(--text);
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

.cta-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-bottom: 50px;
  animation: fadeInUp 1s ease-out 0.4s both;
}

.btn {
  padding: 12px 30px;
  border: none;
  border-radius: 50px;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  display: inline-block;
  position: relative;
  overflow: hidden;
  pointer-events: auto !important;
}

.btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.2);
  transition: left 0.3s ease;
  z-index: -1;
}

.btn:hover::before {
  left: 100%;
}

.btn-primary {
  background: linear-gradient(135deg, var(--primary), #00a876);
  color: white;
  box-shadow: 0 5px 20px rgba(0, 184, 148, 0.4);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(0, 184, 148, 0.6);
}

.btn-secondary {
  background: transparent;
  color: var(--accent);
  border: 2px solid var(--accent);
}

.btn-secondary:hover {
  background: var(--accent);
  color: white;
  transform: translateY(-3px);
}

.btn:active {
  transform: scale(0.98);
}

.scroll-indicator {
  animation: bounce 2s infinite;
  cursor: pointer;
}

@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.arrow-down {
  font-size: 2em;
  margin-top: 10px;
  animation: float 2s ease-in-out infinite;
  display: block;
}

/* SECTIONS */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.section-title {
  font-size: 3em;
  color: var(--primary);
  margin-bottom: 50px;
  text-align: center;
  animation: bounceIn 0.8s ease-out;
  position: relative;
  padding-bottom: 20px;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--accent));
  border-radius: 2px;
}

@keyframes bounceIn {
  0% {
    opacity: 0;
    transform: scale(0.9);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* ABOUT SECTION */
.about-section {
  padding: 100px 20px;
  background: var(--light);
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  margin-top: 50px;
}

.about-text {
  animation: slideInLeft 0.8s ease-out;
}

@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.about-intro {
  font-size: 1.2em;
  margin-bottom: 20px;
  line-height: 1.8;
}

.about-text p {
  font-size: 1.05em;
  line-height: 1.8;
  margin-bottom: 20px;
  color: var(--text);
}

.about-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-top: 40px;
}

.stat {
  background: white;
  padding: 20px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
}

.stat:nth-child(1) { animation-delay: 0.1s; }
.stat:nth-child(2) { animation-delay: 0.2s; }
.stat:nth-child(3) { animation-delay: 0.3s; }

.stat:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
}

.stat h3 {
  font-size: 2.5em;
  color: var(--accent);
  margin-bottom: 10px;
}

.stat p {
  color: var(--text);
  font-size: 0.95em;
}

.about-interests {
  animation: slideInRight 0.8s ease-out;
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.about-interests h3 {
  font-size: 1.5em;
  margin-bottom: 30px;
  color: var(--primary);
}

.interests-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.interest-card {
  background: white;
  padding: 20px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  cursor: pointer;
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
}

.interest-card:nth-child(1) { animation-delay: 0.1s; }
.interest-card:nth-child(2) { animation-delay: 0.2s; }
.interest-card:nth-child(3) { animation-delay: 0.3s; }
.interest-card:nth-child(4) { animation-delay: 0.4s; }
.interest-card:nth-child(5) { animation-delay: 0.5s; }
.interest-card:nth-child(6) { animation-delay: 0.6s; }

.interest-card:hover {
  transform: translateY(-10px) scale(1.05);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
}

.interest-icon {
  font-size: 2em;
  display: block;
  margin-bottom: 10px;
}

.interest-card p {
  margin: 0;
  font-weight: 500;
}

/* PROJECTS SECTION */
.projects-section {
  padding: 100px 20px;
  background: var(--light);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  margin-top: 50px;
}

.project-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
}

.project-card:nth-child(1) { animation-delay: 0.1s; }
.project-card:nth-child(2) { animation-delay: 0.2s; }
.project-card:nth-child(3) { animation-delay: 0.3s; }

.project-card:hover {
  transform: translateY(-15px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
}

.project-image {
  position: relative;
  overflow: hidden;
  height: 250px;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-btn {
  background: var(--accent);
  color: white;
  padding: 10px 25px;
  border-radius: 25px;
  text-decoration: none;
  font-weight: bold;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  pointer-events: auto !important;
}

.project-btn:hover {
  background: var(--primary);
  transform: scale(1.1);
}

.project-info {
  padding: 25px;
}

.project-info h3 {
  color: var(--accent);
  margin-bottom: 10px;
  font-size: 1.3em;
}

.project-info p {
  color: var(--text);
  margin-bottom: 15px;
  font-size: 0.95em;
}

.project-tags {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.tag {
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  padding: 5px 12px;
  border-radius: 20px;
  font-size: 0.85em;
  font-weight: bold;
}

/* SKILLS SECTION */
.skills-section {
  padding: 100px 20px;
  background: var(--light);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
  margin-top: 50px;
}

.skill-item {
  background: white;
  padding: 25px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
}

.skill-item:nth-child(1) { animation-delay: 0.1s; }
.skill-item:nth-child(2) { animation-delay: 0.2s; }
.skill-item:nth-child(3) { animation-delay: 0.3s; }
.skill-item:nth-child(4) { animation-delay: 0.4s; }
.skill-item:nth-child(5) { animation-delay: 0.5s; }
.skill-item:nth-child(6) { animation-delay: 0.6s; }

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.skill-header h3 {
  color: var(--accent);
  margin: 0;
  font-size: 1.1em;
}

.skill-percent {
  color: var(--primary);
  font-weight: bold;
  font-size: 0.95em;
}

.skill-bar {
  background: #eee;
  height: 10px;
  border-radius: 5px;
  overflow: hidden;
}

.skill-fill {
  background: linear-gradient(90deg, var(--primary), var(--accent));
  height: 100%;
  border-radius: 5px;
  animation: fillBar 1.5s ease-out forwards;
}

@keyframes fillBar {
  from {
    width: 0;
  }
}

/* CONTACT SECTION */
.contact-section {
  padding: 100px 20px;
  background: var(--light);
}

.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  margin-top: 50px;
}

.contact-form-container {
  animation: slideInLeft 0.8s ease-out;
}

.contact-form-container h3 {
  color: var(--primary);
  margin-bottom: 25px;
  font-size: 1.5em;
}

.contact-form {
  background: white;
  padding: 40px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
}

body.dark-mode .contact-form {
  background: #2a2a2a;
}

.contact-form .form-group {
  margin-bottom: 20px;
}

.contact-form label {
  display: block;
  margin-bottom: 8px;
  color: var(--text);
  font-weight: 600;
}

.form-group {
  margin-bottom: 20px;
}

.form-group input,
.form-group textarea,
.form-group select,
.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 12px;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-family: inherit;
  font-size: 1em;
  transition: all 0.3s ease;
  background: white;
  color: var(--text);
  pointer-events: auto !important;
  cursor: text;
}

body.dark-mode .form-group input,
body.dark-mode .form-group textarea,
body.dark-mode .form-group select,
body.dark-mode .contact-form input,
body.dark-mode .contact-form textarea {
  background: #1a1a1a;
  color: #e0e0e0;
  border-color: #444;
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus,
.contact-form input:focus,
.contact-form textarea:focus {
  border-color: var(--accent);
  outline: none;
  box-shadow: 0 0 15px rgba(225, 112, 85, 0.3);
  transform: scale(1.02);
}

.contact-info {
  animation: slideInRight 0.8s ease-out;
}

.contact-item {
  margin-bottom: 30px;
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
}

.contact-item:nth-child(1) { animation-delay: 0.1s; }
.contact-item:nth-child(2) { animation-delay: 0.2s; }
.contact-item:nth-child(3) { animation-delay: 0.3s; }
.contact-item:nth-child(4) { animation-delay: 0.4s; }

.contact-item h4 {
  color: var(--accent);
  margin-bottom: 10px;
  font-size: 1.1em;
}

.contact-item a {
  color: var(--primary);
  text-decoration: none;
  font-weight: bold;
  transition: all 0.3s ease;
}

.contact-item a:hover {
  color: var(--accent);
  text-decoration: underline;
}

.contact-item p {
  color: var(--text);
  margin: 0;
}

.social-links {
  display: flex;
  gap: 15px;
  margin-top: 15px;
  flex-wrap: wrap;
}

.social-link {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 20px;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: white;
  text-decoration: none;
  border-radius: 25px;
  font-weight: bold;
  transition: all 0.3s ease;
  pointer-events: auto !important;
  opacity: 1 !important;
  cursor: pointer;
  box-shadow: 0 5px 15px rgba(0, 184, 148, 0.3);
  border: none;
}

.social-link:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 184, 148, 0.5);
  background: linear-gradient(135deg, var(--accent), var(--primary));
}

.social-link:active {
  transform: translateY(-1px);
}

.social-icon {
  font-size: 1.5em;
  transition: all 0.3s ease;
  display: inline-block;
}

.social-icon:hover {
  transform: scale(1.2) translateY(-5px);
}

/* FEEDBACK SECTION */
.feedback-section {
  background: white;
  padding: 50px;
  border-radius: 12px;
  margin-top: 80px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
}

body.dark-mode .feedback-section {
  background: #2a2a2a;
}

.feedback-form {
  max-width: 600px;
  margin: 0 auto;
}

.feedback-form .form-group {
  margin-bottom: 20px;
}

.feedback-form input,
.feedback-form textarea,
.feedback-form select {
  width: 100%;
  padding: 12px;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-family: inherit;
  font-size: 1em;
  transition: all 0.3s ease;
  background: white;
  color: var(--text);
  pointer-events: auto !important;
}

body.dark-mode .feedback-form input,
body.dark-mode .feedback-form textarea,
body.dark-mode .feedback-form select {
  background: #1a1a1a;
  color: #e0e0e0;
  border-color: #444;
}

.feedback-form input:focus,
.feedback-form textarea:focus,
.feedback-form select:focus {
  border-color: var(--accent);
  outline: none;
  box-shadow: 0 0 15px rgba(225, 112, 85, 0.3);
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.rating-stars {
  display: flex;
  gap: 10px;
  justify-content: center;
  flex-direction: row-reverse;
}

.rating-stars input {
  display: none;
}

.rating-stars label {
  font-size: 2em;
  cursor: pointer;
  transition: all 0.3s ease;
  opacity: 0.5;
}

.rating-stars input:checked ~ label,
.rating-stars label:hover,
.rating-stars label:hover ~ label {
  opacity: 1;
  transform: scale(1.2);
  color: var(--accent);
}

/* FLOATING CONTACT BUTTON */
.floating-contact {
  position: fixed;
  bottom: 30px;
  right: 30px;
  z-index: 500;
}

.floating-btn {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.8em;
  text-decoration: none;
  box-shadow: 0 5px 20px rgba(0, 184, 148, 0.4);
  transition: all 0.3s ease;
  animation: pulse 2s ease-in-out infinite;
  pointer-events: auto !important;
}

.floating-btn:hover {
  transform: scale(1.1);
  box-shadow: 0 10px 30px rgba(0, 184, 148, 0.6);
  animation: none;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

/* FOOTER */
.footer {
  background: var(--dark);
  color: white;
  text-align: center;
  padding: 30px 20px;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .nav-menu {
    gap: 15px;
  }

  .hero-title {
    font-size: 2.5em;
  }

  .hero-subtitle {
    font-size: 1.1em;
  }

  .cta-buttons {
    flex-direction: column;
    align-items: center;
  }

  .about-content,
  .contact-wrapper {
    grid-template-columns: 1fr;
  }

  .about-stats {
    grid-template-columns: 1fr;
  }

  .interests-grid {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 2em;
  }

  .floating-contact {
    bottom: 20px;
    right: 20px;
  }

  .floating-btn {
    width: 50px;
    height: 50px;
    font-size: 1.5em;
  }

  .form-row {
    grid-template-columns: 1fr;
  }
}

/* MODAL STYLES */
.modal {
  display: none;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  backdrop-filter: blur(5px);
  animation: fadeIn 0.3s ease;
}

.modal.active {
  display: flex;
  align-items: center;
  justify-content: center;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.modal-content {
  background: linear-gradient(135deg, #ffffff 0%, #f5f5f5 100%);
  padding: 0;
  border-radius: 20px;
  width: 90%;
  max-width: 700px;
  max-height: 85vh;
  overflow-y: auto;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  animation: slideUp 0.4s ease;
  position: relative;
}

body.dark-mode .modal-content {
  background: linear-gradient(135deg, #2a2a2a 0%, #1f1f1f 100%);
  color: #e0e0e0;
}

@keyframes slideUp {
  from {
    transform: translateY(50px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.modal-close {
  position: absolute;
  right: 20px;
  top: 20px;
  font-size: 32px;
  font-weight: bold;
  color: #666;
  background: none;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  z-index: 10;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  pointer-events: auto !important;
}

body.dark-mode .modal-close {
  color: #aaa;
}

.modal-close:hover {
  background-color: rgba(0, 0, 0, 0.1);
  transform: rotate(90deg);
}

body.dark-mode .modal-close:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

.modal-project {
  display: none;
}

.modal-project.active {
  display: block;
  animation: fadeIn 0.3s ease;
}

.modal-header {
  background: linear-gradient(135deg, #00b894 0%, #e17055 100%);
  color: white;
  padding: 40px 30px;
  border-radius: 20px 20px 0 0;
  text-align: center;
}

.modal-header h2 {
  margin: 0;
  font-size: 2.5em;
  font-weight: 700;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.modal-body {
  padding: 40px;
}

.modal-body h3 {
  color: #00b894;
  font-size: 1.5em;
  margin-top: 25px;
  margin-bottom: 15px;
  border-bottom: 3px solid #00b894;
  padding-bottom: 10px;
}

body.dark-mode .modal-body h3 {
  color: #00d4aa;
  border-bottom-color: #00d4aa;
}

.modal-body p {
  line-height: 1.8;
  color: #333;
  margin-bottom: 15px;
  font-size: 1.05em;
}

body.dark-mode .modal-body p {
  color: #d0d0d0;
}

.help-list {
  list-style: none;
  padding: 0;
  margin: 15px 0;
}

.help-list li {
  padding: 12px 0;
  padding-left: 30px;
  position: relative;
  line-height: 1.6;
  color: #333;
  border-left: 4px solid #00b894;
  margin-bottom: 10px;
  background: rgba(0, 184, 148, 0.05);
  padding: 12px 15px;
  border-radius: 8px;
}

body.dark-mode .help-list li {
  color: #d0d0d0;
  background: rgba(0, 212, 170, 0.1);
  border-left-color: #00d4aa;
}

.help-list strong {
  color: #00b894;
}

body.dark-mode .help-list strong {
  color: #00d4aa;
}

.features-list {
  list-style: none;
  padding: 0;
  margin: 15px 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.features-list li {
  background: linear-gradient(135deg, #00b894 0%, #e17055 100%);
  color: white;
  padding: 15px;
  border-radius: 10px;
  font-weight: 500;
  text-align: center;
  box-shadow: 0 5px 15px rgba(0, 184, 148, 0.2);
  transition: all 0.3s ease;
}

.features-list li:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 184, 148, 0.3);
}

/* Scrollbar styling for modal */
.modal-content::-webkit-scrollbar {
  width: 8px;
}

.modal-content::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 10px;
}

body.dark-mode .modal-content::-webkit-scrollbar-track {
  background: #333;
}

.modal-content::-webkit-scrollbar-thumb {
  background: #00b894;
  border-radius: 10px;
}

.modal-content::-webkit-scrollbar-thumb:hover {
  background: #e17055;
}

/* Responsive design for modal */
@media (max-width: 768px) {
  .modal-content {
    width: 95%;
    max-height: 90vh;
  }

  .modal-header h2 {
    font-size: 1.8em;
  }

  .modal-body {
    padding: 25px;
  }

  .modal-body h3 {
    font-size: 1.3em;
  }

  .features-list {
    grid-template-columns: 1fr;
  }

  .help-list li {
    font-size: 0.95em;
  }
}

@media (max-width: 480px) {
  .modal-header {
    padding: 25px 20px;
  }

  .modal-header h2 {
    font-size: 1.5em;
  }

  .modal-body {
    padding: 20px;
  }

  .modal-body h3 {
    font-size: 1.2em;
  }

  .modal-body p {
    font-size: 1em;
  }
}

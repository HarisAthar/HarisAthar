<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Haris Bin Athar - Portfolio</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/react@18.2.0/umd/react.production.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/react-dom@18.2.0/umd/react-dom.production.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@babel/standalone@7.22.9/babel.min.js"></script>
  <style>
    @keyframes subtleGlow {
      0% { box-shadow: 0 0 5px rgba(59, 130, 246, 0.3); }
      50% { box-shadow: 0 0 15px rgba(59, 130, 246, 0.5); }
      100% { box-shadow: 0 0 5px rgba(59, 130, 246, 0.3); }
    }
    .glow-hover:hover {
      animation: subtleGlow 1.5s infinite;
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .fade-in-up {
      animation: fadeInUp 0.6s ease-out forwards;
    }
    .project-card {
      opacity: 0;
      animation-delay: calc(0.1s * var(--index));
    }
  </style>
</head>
<body>
  <div id="root"></div>
  <script type="text/babel">
    const { useState, useEffect } = React;

    const techStack = [
      { name: "Node.js", logo: "https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" },
      { name: "Python", logo: "https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" },
      { name: "SQL", logo: "https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white" },
      { name: "FastAPI", logo: "https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" },
      { name: "React Native", logo: "https://img.shields.io/badge/React%20Native-61DAFB?style=for-the-badge&logo=react&logoColor=black" },
      { name: "MERN Stack", logo: "https://img.shields.io/badge/MERN-000000?style=for-the-badge&logo=mongodb&logoColor=white" },
      { name: "PostgreSQL", logo: "https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" },
      { name: "MySQL", logo: "https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" },
      { name: "MongoDB", logo: "https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" },
      { name: "Prisma", logo: "https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white" },
      { name: "SQLAlchemy", logo: "https://img.shields.io/badge/SQLAlchemy-000000?style=for-the-badge&logo=python&logoColor=white" },
      { name: "LiveKit", logo: "https://img.shields.io/badge/LiveKit-4A90E2?style=for-the-badge&logo=webrtc&logoColor=white" },
      { name: "FusionPBX/FreeSWITCH", logo: "https://img.shields.io/badge/FreeSWITCH-000000?style=for-the-badge&logo=voip&logoColor=white" },
      { name: "Twilio", logo: "https://img.shields.io/badge/Twilio-F22F46?style=for-the-badge&logo=twilio&logoColor=white" },
      { name: "Celery", logo: "https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white" },
      { name: "Stripe", logo: "https://img.shields.io/badge/Stripe-008CDD?style=for-the-badge&logo=stripe&logoColor=white" },
      { name: "AWS", logo: "https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" },
      { name: "OpenAI", logo: "https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" },
      { name: "Deepgram", logo: "https://img.shields.io/badge/Deepgram-000000?style=for-the-badge&logo=deepgram&logoColor=white" },
    ];

    const softSkills = ["Leadership", "Communication", "Teamwork", "Client Collaboration"];

    const projects = [
      { title: "SecureConnect", description: "Real-time chat/call app with secure auth, Twilio integration, and auto-subscriptions. Built for seamless comms." },
      { title: "BadaBing", description: "AI platform for chats/calls: intent routing, semantic search, RevenueCat billing, and async processing." },
      { title: "CHADGPT", description: "Mobile AI chat with OpenAI convos, DALL·E visuals, and voice features in a sleek React Native UI." },
      { title: "TextMe", description: "Global VoIP app: FastAPI backend, FusionPBX calls, secure messaging, and real-time notifications." },
      { title: "AI Campaign", description: "Outbound bot for leads: LiveKit calls, transcript CRM sync, and automated scheduling." },
      { title: "PressPilot", description: "Multi-org content backend: RBAC, dynamic templates, and activity tracking." },
      { title: "AutoBot Manager", description: "Chatbot hub: Node.js flows, Stripe payments, AWS storage, and robust auth." },
    ];

    const App = () => {
      const [isDarkMode, setIsDarkMode] = useState(true);
      const [animated, setAnimated] = useState(false);

      useEffect(() => {
        setAnimated(true);
      }, []);

      const toggleTheme = () => {
        setIsDarkMode(!isDarkMode);
      };

      return (
        <div className={`${isDarkMode ? 'bg-gray-900 text-white' : 'bg-gray-100 text-gray-900'} min-h-screen font-sans transition-all duration-300`}>
          {/* Header */}
          <header className="sticky top-0 bg-opacity-90 backdrop-blur-md z-10 p-4 flex justify-between items-center">
            <h1 className="text-2xl font-bold">Haris Bin Athar</h1>
            <button
              onClick={toggleTheme}
              className="p-2 rounded-full bg-gray-700 hover:bg-gray-600 text-white transition glow-hover"
            >
              {isDarkMode ? '☀️ Light' : '🌙 Dark'}
            </button>
          </header>

          {/* Hero Section */}
          <section className="flex flex-col items-center py-16 px-4 text-center fade-in-up" style={{ animationDelay: '0.2s' }}>
            <h1 className="text-4xl md:text-5xl font-extrabold mb-2">
              👋 Hey, I'm <span className="text-blue-500">Haris Bin Athar</span>
            </h1>
            <h3 className="text-xl md:text-2xl font-semibold mb-4">
              💻 Software Engineer | Backend, Web & Mobile Dev
            </h3>
            <p className="text-lg max-w-2xl mb-4">
              🚀 Crafting scalable systems, APIs, and databases. Thriving in dynamic teams for high-impact tech.
              <br />
              📍 Lahore, Pakistan | 📞 +92 311 0145289 | ✉️ <a href="mailto:harisathar87@gmail.com" className="text-blue-400 hover:underline">harisathar87@gmail.com</a>
            </p>
          </section>

          {/* Tech Stack */}
          <section className="py-12 px-4 fade-in-up" style={{ animationDelay: '0.4s' }}>
            <h2 className="text-3xl font-bold text-center mb-8">⚡ Tech Stack</h2>
            <div className="flex flex-wrap justify-center gap-4">
              {techStack.map((tech, index) => (
                <img
                  key={index}
                  src={tech.logo}
                  alt={tech.name}
                  className="h-10 transform hover:scale-110 transition-transform duration-300 glow-hover"
                />
              ))}
            </div>
          </section>

          {/* Soft Skills */}
          <section className="py-12 px-4 bg-gray-800 bg-opacity-50 fade-in-up" style={{ animationDelay: '0.6s' }}>
            <h2 className="text-3xl font-bold text-center mb-8">🧠 Soft Skills</h2>
            <div className="flex flex-wrap justify-center gap-4">
              {softSkills.map((skill, index) => (
                <span key={index} className="px-4 py-2 bg-blue-600 rounded-full text-white hover:bg-blue-500 transition glow-hover">
                  {skill}
                </span>
              ))}
            </div>
          </section>

          {/* Projects */}
          <section className="py-12 px-4 fade-in-up" style={{ animationDelay: '0.8s' }}>
            <h2 className="text-3xl font-bold text-center mb-8">🛠 Featured Projects</h2>
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 max-w-5xl mx-auto">
              {projects.map((project, index) => (
                <div
                  key={index}
                  className={`p-6 bg-gray-700 bg-opacity-50 rounded-lg shadow-lg hover:shadow-xl transform hover:-translate-y-2 transition-all duration-500 glow-hover project-card fade-in-up`}
                  style={{ '--index': index }}
                >
                  <h3 className="text-xl font-semibold">🔹 {project.title}</h3>
                  <p className="mt-2">{project.description}</p>
                </div>
              ))}
            </div>
          </section>

          {/* Experience */}
          <section className="py-12 px-4 bg-gray-800 bg-opacity-50 fade-in-up" style={{ animationDelay: '1s' }}>
            <h2 className="text-3xl font-bold text-center mb-8">💼 Experience</h2>
            <div className="max-w-3xl mx-auto space-y-6">
              <div className="p-4 bg-gray-700 bg-opacity-50 rounded-lg glow-hover">
                <h3 className="text-xl font-semibold">Software Engineer (Backend) @ Senarios (Aug 2024 – Present)</h3>
                <p>Scalable APIs, microservices, integrations (Stripe, RevenueCat), async workflows.</p>
              </div>
              <div className="p-4 bg-gray-700 bg-opacity-50 rounded-lg glow-hover">
                <h3 className="text-xl font-semibold">Freelance Software Developer (2023 – Present)</h3>
                <p>Full-stack apps with React/Native/Node, APIs, client-tailored solutions.</p>
              </div>
              <div className="p-4 bg-gray-700 bg-opacity-50 rounded-lg glow-hover">
                <h3 className="text-xl font-semibold">Teaching Assistant @ PUCIT (2023)</h3>
                <p>Supported ICT/Stats courses, grading, lecture prep.</p>
              </div>
            </div>
          </section>

          {/* Connect */}
          <section className="py-12 px-4 text-center fade-in-up" style={{ animationDelay: '1.2s' }}>
            <h2 className="text-3xl font-bold mb-8">📬 Connect With Me</h2>
            <div className="flex justify-center gap-4">
              <a href="https://www.linkedin.com/in/haris-athar-5b0000242">
                <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" className="h-10 hover:scale-110 transition-transform glow-hover" />
              </a>
              <a href="mailto:harisathar87@gmail.com">
                <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" className="h-10 hover:scale-110 transition-transform glow-hover" />
              </a>
              <a href="https://github.com/HarisAthar">
                <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" className="h-10 hover:scale-110 transition-transform glow-hover" />
              </a>
            </div>
          </section>

          {/* Footer */}
          <footer className="py-4 text-center bg-gray-900 bg-opacity-50">
            <p>© 2025 Haris Bin Athar. All rights reserved.</p>
          </footer>
        </div>
      );
    };

    ReactDOM.render(<App />, document.getElementById('root'));
  </script>
</body>
</html>

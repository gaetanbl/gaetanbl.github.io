<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gaëtan Baylou-Lanot - Project Portfolio</title>
    <style>
        /* ==========================================================================
           ARTISTIC DIRECTION: CHIRPY INSPIRED (MINIMALIST & LAB STYLE)
           ========================================================================== */
        :root {
            --bg-color: #ffffff;
            --text-color: #343a40;
            --heading-color: #1c1f23;
            --sidebar-bg: #f4f6f8;
            --sidebar-text: #495057;
            --accent-color: #007bff;
            --accent-bg-light: #e3f2fd;
            --code-bg: #1e1e1e;
            --code-text: #f8f8f2;
            --border-color: #dbdfe2;
            --tag-bg: #eff1f3;
            --tag-text: #6c757d;
        }

        body {
            font-family: "-apple-system", BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            color: var(--text-color);
            background-color: var(--bg-color);
            margin: 0;
            padding: 0;
            -webkit-font-smoothing: antialiased;
        }

        /* LEFT SIDEBAR (COMPACT & CLEAN) */
        .sidebar {
            width: 240px;
            background-color: var(--sidebar-bg);
            border-right: 1px solid var(--border-color);
            height: 100vh;
            position: fixed;
            top: 0;
            left: 0;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 3rem 1.2rem 1.5rem 1.2rem;
            box-sizing: border-box;
            z-index: 100;
        }

        .sidebar-top {
            display: flex;
            flex-direction: column;
        }

        .profile {
            text-align: left;
            margin-bottom: 2.5rem;
            padding-left: 0.5rem;
        }

        .profile-pic {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, #e0e0e0, #f5f5f5);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            margin-bottom: 1rem;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.05);
        }

        .profile h1 {
            font-size: 1.15rem;
            font-weight: 700;
            margin: 0;
            color: var(--heading-color);
            letter-spacing: -0.025em;
        }

        .profile p {
            font-size: 0.8rem;
            color: #868e96;
            margin: 0.3rem 0 0 0;
            font-weight: 400;
        }

        .nav-links {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .nav-links li {
            margin-bottom: 0.2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--sidebar-text);
            font-weight: 500;
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 0.5rem 0.6rem;
            border-radius: 6px;
            transition: all 0.15s ease-in-out;
        }

        .nav-links a:hover {
            background-color: #e9ecef;
            color: var(--heading-color);
        }

        .sidebar-footer {
            display: flex;
            gap: 15px;
            padding-left: 0.6rem;
            font-size: 0.9rem;
            color: #adb5bd;
        }
        
        .sidebar-footer a {
            color: #adb5bd;
            text-decoration: none;
            transition: color 0.2s;
        }
        .sidebar-footer a:hover { color: var(--heading-color); }

        /* MAIN CONTENT AREA */
        .content {
            margin-left: 240px;
            padding: 3rem 2.5rem 3rem 1.5rem;
            max-width: 800px;
            box-sizing: border-box;
        }

        /* Chirpy Style Tags */
        .tag-container {
            margin-bottom: 0.75rem;
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
        }

        .tag {
            background: var(--tag-bg);
            color: var(--tag-text);
            padding: 0.15rem 0.55rem;
            border-radius: 4px;
            font-size: 0.75rem;
            font-weight: 500;
            transition: background 0.2s;
        }
        
        .tag:hover {
            background: #e2e6ea;
            color: var(--heading-color);
        }

        h1.main-title { 
            font-size: 2.2rem; 
            font-weight: 700;
            color: var(--heading-color);
            margin: 0 0 0.6rem 0;
            letter-spacing: -0.03em;
            line-height: 1.2;
        }

        .meta {
            font-size: 0.85rem;
            color: #868e96;
            margin-bottom: 2.5rem;
            padding-bottom: 1.2rem;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            gap: 15px;
        }

        h2 { 
            font-size: 1.45rem; 
            font-weight: 600;
            color: var(--heading-color);
            margin-top: 3.5rem; 
            margin-bottom: 1rem;
            letter-spacing: -0.02em;
        }

        p {
            margin: 1rem 0;
            color: var(--text-color);
            font-size: 1rem;
            line-height: 1.6;
        }

        ul {
            padding-left: 1.25rem;
            margin: 1rem 0;
        }

        li {
            margin-bottom: 0.6rem;
            color: var(--text-color);
            line-height: 1.5;
        }
        
        li strong {
            color: var(--heading-color);
        }

        /* PORTFOLIO IMAGES STYLE */
        .project-img {
            width: 100%;
            max-height: 350px;
            object-fit: cover;
            border-radius: 8px;
            margin: 1.2rem 0;
            box-shadow: 0 4px 10px rgba(0,0,0,0.06);
            border: 1px solid var(--border-color);
        }

        /* INFO ALERT BOX */
        blockquote.prompt-info {
            border-left: 4px solid var(--accent-color);
            margin: 2rem 0;
            padding: 1rem 1.25rem;
            background-color: var(--accent-bg-light);
            color: #1e4265;
            border-radius: 0 6px 6px 0;
            font-size: 0.95rem;
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }
        
        blockquote.prompt-info::before {
            content: "ℹ️";
            font-size: 1.1rem;
            line-height: 1;
        }

        /* CODE BLOCKS */
        pre {
            background-color: var(--code-bg);
            padding: 1.25rem;
            border-radius: 8px;
            overflow-x: auto;
            margin: 1.75rem 0;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }

        code {
            font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace;
            font-size: 0.85rem;
            background-color: #f1f3f5;
            color: #d63384;
            padding: 0.2rem 0.4rem;
            border-radius: 4px;
        }

        pre code {
            color: var(--code-text);
            background-color: transparent;
            padding: 0;
            border-radius: 0;
        }

        /* RESPONSIVE DESIGN */
        @media (max-width: 850px) {
            .sidebar { width: 100%; height: auto; position: relative; padding: 2rem 1.5rem; border-right: none; border-bottom: 1px solid var(--border-color); }
            .content { margin-left: 0; padding: 2.5rem 1.5rem; }
        }
    </style>
</head>
<body>

    <!-- LEFT SIDEBAR -->
    <div class="sidebar">
        <div class="sidebar-top">
            <div class="profile">
                <div class="profile-pic">🚀</div>
                <h1>Gaëtan Baylou-Lanot</h1>
                <p>Mechanical & Control Engineering Student</p>
            </div>
            <ul class="nav-links">
                <li><a href="#introduction">📌 Introduction</a></li>
                <li><a href="#van-conversion">🚐 Van Conversion</a></li>
                <li><a href="#gma-internships">🎓 GMA Internships</a></li>
                <li><a href="#ins-aerien">✈️ Association INS'Aérien</a></li>
                <li><a href="#code-project-1">⚙️ Code Project n°1 (C++)</a></li>
                <li><a href="#code-project-2">🔌 Code Project n°2 (ROS2)</a></li>
                <li><a href="#ia-project-1">🧠 AI Project n°1 (ML)</a></li>
                <li><a href="#ia-project-2">🤖 AI Project n°2 (RL)</a></li>
            </ul>
        </div>
        
        <div class="sidebar-footer">
            <a href="https://www.linkedin.com/in/gaetan-baylou-lanot-72931b177/" target="_blank" title="LinkedIn">🔗</a>
            <a href="mailto:Gaetan.baylou--lanot@insa-rennes.fr" title="Mail">✉️</a>
            <a href="https://canva.link/ky3nhbgvb7r8ahv" target="_blank" title="CV Link">📄</a>
        </div>
    </div>

    <!-- MAIN CONTENT AREA -->
    <div class="content">
        <div class="tag-container">
            <span class="tag">mechanical-engineering</span>
            <span class="tag">control-systems</span>
            <span class="tag">robotics</span>
            <span class="tag">automation</span>
        </div>
        
        <h1 class="main-title">Academic Tracks & Technical Engineering Projects</h1>
        <div class="meta">
            <span>Current Year: 2026</span>
            <span>•</span>
            <span>By Gaëtan Baylou-Lanot</span>
        </div>

        <section id="introduction">
            <h2>📌 Introduction</h2>
            <p>Welcome to my personal project documentation environment. As a Mechanical and Control Engineering (GMA) student at INSA Rennes, this space serves to highlight my practical execution of control loops, structural modeling, and robotic integrations.</p>
            
            <blockquote class="prompt-info">
                <span><strong>Looking for a final-year internship:</strong> Seeking a 4 to 5-month placement starting March 2027 focusing on AI and Robotics workflows. Refer to "My CV.eng.pdf" or my live Canva link for summary details.</span>
            </blockquote>
        </section>

        <!-- VAN CONVERSION SECTION (LEFT EMPTY) -->
        <section id="van-conversion">
            <h2>🚐 Van conversion: A brief summary of my personality</h2>
            <!-- Left empty as requested -->
            <p></p>
            <img class="project-img" src="images/van-project.jpg" alt="[Insert your Van photo here]">
        </section>

        <!-- GMA INTERNSHIPS (MOVED HERE & UPDATED WITH REAL EXP) -->
        <section id="gma-internships">
            <h2>🎓 Mechanical & Control Engineering (GMA) Track: 3 Core Internships</h2>
            <p>To explicitly illustrate my validation of GMA principles (materials science, prototyping, CAD, and robot kinematics), these three industrial experiences highlight my progression:</p>
            
            <img class="project-img" src="https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=800&q=80" alt="Industrial Engineering">

            <ul>
                <li>
                    <strong>XSun — Structural Engineering Placement (3 months):</strong> 
                    Contributed to the conceptual study of lightweight, optimized composite materials. Handled the 3D modeling and precision technical drawing of the structural layout for a new autonomous solar-powered VTOL drone model using advanced CAD packages.
                </li>
                <li>
                    <strong>Decathlon France — 3D Printing & Materials Technician at ADDLAB (2 months):</strong> 
                    Supervised the resin 3D printing production line from software parameterization to physical finishing. Ran an internal R&D project validating a brand-new material matrix for Selective Laser Sintering (SLS). Contributed directly to futuristic rapid prototyping jobs, including custom bicycle frames and bespoke aerospace component concepts for the ESA.
                </li>
                <li>
                    <strong>Safran / Metallicadour — Robotic Arm Integration (1 month + Academic Continuation):</strong> 
                    Shadowed specialized research engineers deploying industrial automated solutions utilizing a high-payload KUKA robotic arm within the aerospace manufacturing ecosystem. 
                    <br><em>GMA Academic Link:</em> Leveraging this exposure, I successfully applied complex theoretical kinematics during my 4th year at INSA Rennes by completely rewriting the mathematical control software for a Stäubli SCARA robot in MATLAB, which we successfully validated through experimental physical lab tests.
                </li>
            </ul>
        </section>

        <!-- INS'AERIEN ASSOCIATION SECTION -->
        <section id="ins-aerien">
            <h2>✈️ President of the INS'Aérien Association</h2>
            <p>Founded and managed an open-access FPV drone club at INSA Rennes, creating a complete environment to bridge high-speed custom hardware assembly with physical deployment cycles.</p>

            <img class="project-img" src="https://images.unsplash.com/photo-1527977966376-1c8408f9f108?auto=format&fit=crop&w=800&q=80" alt="FPV Drone Testing">

            <ul>
                <li><strong>Hardware Performance:</strong> Built customized FPV drones entirely from scratch capable of accelerating from 0 to 100 km/h in 2.2 seconds.</li>
                <li><strong>Operations Scale:</strong> Expanded the organization to include 9 active internal members, successfully building 3 functional drones and producing over 20 video clips and festival captures.</li>
                <li><strong>Leadership Value:</strong> Developed professional competence in budget management, corporate communications (further developed as Communications Manager for the GMA Corporate White Week), and team cross-collaboration under dynamic schedules.</li>
            </ul>
        </section>

        <!-- CODE PROJECT 1 -->
        <section id="code-project-1">
            <h2>⚙️ Code Project n°1: Robotics Club inside the French Robotics Cup</h2>
            <p>Embedded systems programming and algorithmic coordination within the INSA Rennes school robotics club.</p>
            <ul>
                <li><strong>Competition Testing:</strong> Deployed and tested competitive routines in high-stress settings during the French Robotics Cup (Senior Category), achieving a strong 42nd place finish out of 121 teams nationwide.</li>
                <li><strong>Low-level Architecture:</strong> Developed object-oriented structures in C++ integrated with Git version control to ensure responsive sensor reading and precise trajectory execution.</li>
                <li><strong>Legacy:</strong> Built on top of my foundational background as a 2021 RoboCup Junior World Champion in Bangkok, Thailand, emphasizing robust coordination and performance under strict competition timelines.</li>
            </ul>
        </section>

        <!-- CODE PROJECT 2 (LEFT EMPTY) -->
        <section id="code-project-2">
            <h2>🔌 Code Project n°2: Robot Control with ROS2</h2>
            <!-- Left empty as requested -->
            <p></p>
            <img class="project-img" src="images/ros2-project.jpg" alt="[Insert your ROS2 map/nodes photo here]">
        </section>

        <!-- AI PROJECT 1 (LEFT EMPTY) -->
        <section id="ia-project-1">
            <h2>🧠 AI Project n°1: Supervised Learning Pipeline</h2>
            <!-- Left empty as requested -->
            <p></p>
        </section>

        <!-- AI PROJECT 2 -->
        <section id="ia-project-2">
            <h2>🤖 AI Project n°2: Simulation and Guidance of Autonomous Robots by Reinforcement Learning</h2>
            <p>Direct implementation and training of end-to-end learning agents inside next-generation physical simulators.</p>

            <img class="project-img" src="https://images.unsplash.com/photo-1617791160505-6f006e121980?auto=format&fit=crop&w=800&q=80" alt="Neural Network Simulation">

            <ul>
                <li><strong>Scalian Deployment:</strong> Modeled a physical 'Duckiebot' robot platform in simulation environments to train, evaluate, and scale deep reinforcement learning loops.</li>
                <li><strong>Algorithmic Fine-Tuning:</strong> Adjusted learning hyper-parameters and reward algorithms using Proximal Policy Optimization (PPO) variants inside PyTorch to achieve reliable guidance behavior.</li>
                <li><strong>Physical Target:</strong> Designed optimal reward metrics to transfer trained policies successfully into clean autonomous navigation behaviors on real embedded platforms.</li>
            </ul>
        </section>
    </div>

</body>
</html>

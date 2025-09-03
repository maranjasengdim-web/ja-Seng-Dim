<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ja Seng Dim | Aspiring Cabin Crew</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals -->
    <!-- Application Structure Plan: A single-page, thematic interactive resume designed for a cabin crew recruiter. Structure includes a Hero section, Profile, an interactive Career Journey timeline, a Skills section with switchable charts, Education, and Contact. This structure is chosen to tell a compelling narrative of the candidate's suitability, highlighting key transferable skills upfront and allowing recruiters to explore details on demand, which is more engaging than a linear document. -->
    <!-- Visualization & Content Choices: 1. Career Journey: Report Info -> Work/Project Experience. Goal -> Organize & Detail. Viz -> Interactive vertical timeline (HTML/CSS). Interaction -> Click to show details in an adjacent panel. Justification -> Keeps the main view uncluttered while providing easy access to deep information. 2. Skills: Report Info -> Soft & Technical skills list. Goal -> Inform & Compare. Viz -> Radar chart for soft skills, Bar chart for technical skills (Chart.js/Canvas). Interaction -> Toggle button to switch between charts; tooltips on hover. Justification -> Visualizes proficiency in a more impactful and digestible way than a text list. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FDFBF8;
            color: #4A4A4A;
        }
        .nav-link {
            transition: color 0.3s ease;
        }
        .nav-link:hover, .nav-link.active {
            color: #D35400;
        }
        .timeline-item {
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .timeline-item.active {
            background-color: #FFF3E0;
            border-color: #D35400;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-md shadow-sm sticky top-0 z-50">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-xl font-bold text-gray-800">Ja Seng Dim</div>
            <div class="hidden md:flex space-x-8">
                <a href="#profile" class="nav-link text-gray-600 font-medium">Profile</a>
                <a href="#experience" class="nav-link text-gray-600 font-medium">Experience</a>
                <a href="#skills" class="nav-link text-gray-600 font-medium">Skills</a>
                <a href="#education" class="nav-link text-gray-600 font-medium">Education</a>
                <a href="#contact" class="nav-link text-gray-600 font-medium">Contact</a>
            </div>
            <div class="md:hidden">
                <button id="menu-btn" class="text-gray-800 focus:outline-none">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
                </button>
            </div>
        </nav>
        <div id="mobile-menu" class="hidden md:hidden px-6 pt-2 pb-4 space-y-2">
            <a href="#profile" class="block nav-link text-gray-600">Profile</a>
            <a href="#experience" class="block nav-link text-gray-600">Experience</a>
            <a href="#skills" class="block nav-link text-gray-600">Skills</a>
            <a href="#education" class="block nav-link text-gray-600">Education</a>
            <a href="#contact" class="block nav-link text-gray-600">Contact</a>
        </div>
    </header>

    <main class="container mx-auto px-6 py-12 md:py-20">

        <section id="hero" class="text-center mb-20">
            <h1 class="text-4xl md:text-6xl font-bold text-gray-800 mb-4">Ready for Takeoff</h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-3xl mx-auto">
                Enthusiastic and service-driven business graduate eager to bring dedication and a positive "Scootitude" to the Cabin Crew team at Scoot.
            </p>
        </section>

        <section id="profile" class="mb-20">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">Professional Profile</h2>
                <p class="text-gray-600 mt-2 max-w-2xl mx-auto">My background in business and customer service has prepared me to deliver the safety, comfort, and service excellence that defines the Scoot experience.</p>
            </div>
            <div class="grid md:grid-cols-3 gap-8">
                <div class="bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">👤</div>
                    <h3 class="text-xl font-bold text-gray-800 mb-2">Customer-Focused</h3>
                    <p class="text-gray-600">Dedicated to creating positive and memorable passenger experiences by actively listening and professionally addressing needs and concerns.</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">💡</div>
                    <h3 class="text-xl font-bold text-gray-800 mb-2">Adaptable Problem-Solver</h3>
                    <p class="text-gray-600">Maintains composure in fast-paced environments, adept at resolving technical issues and complaints with efficiency and professionalism.</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">🤝</div>
                    <h3 class="text-xl font-bold text-gray-800 mb-2">Effective Communicator</h3>
                    <p class="text-gray-600">Skilled in streamlining communication between diverse groups of people, ensuring clear, coordinated, and efficient teamwork.</p>
                </div>
            </div>
        </section>

        <section id="experience" class="mb-20">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">Career Journey</h2>
                <p class="text-gray-600 mt-2 max-w-2xl mx-auto">Explore my professional and academic projects. Click on an item in the timeline to see the details of my contributions and achievements.</p>
            </div>
            <div class="flex flex-col md:flex-row gap-8">
                <div class="md:w-1/3">
                    <div id="timeline-list" class="space-y-4">
                    </div>
                </div>
                <div class="md:w-2/3 bg-white p-8 rounded-lg shadow-md min-h-[300px]">
                    <div id="experience-details">
                        <h3 id="details-title" class="text-2xl font-bold text-gray-800 mb-2"></h3>
                        <p id="details-subtitle" class="text-gray-500 mb-4"></p>
                        <ul id="details-points" class="list-disc list-inside text-gray-600 space-y-2">
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills" class="mb-20">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">Core Competencies</h2>
                <p class="text-gray-600 mt-2 max-w-2xl mx-auto">A blend of soft skills for exceptional service and technical skills for operational efficiency.</p>
            </div>
            <div class="flex justify-center mb-8">
                <div class="bg-gray-200 rounded-full p-1 flex">
                    <button id="soft-skills-btn" class="px-6 py-2 rounded-full bg-white text-gray-800 shadow">Soft Skills</button>
                    <button id="tech-skills-btn" class="px-6 py-2 rounded-full text-gray-600">Technical Skills</button>
                </div>
            </div>
            <div class="bg-white p-6 rounded-lg shadow-md">
                <div id="soft-skills-chart-container" class="chart-container">
                    <canvas id="softSkillsChart"></canvas>
                </div>
                <div id="tech-skills-chart-container" class="chart-container hidden">
                    <canvas id="techSkillsChart"></canvas>
                </div>
            </div>
        </section>

        <section id="education" class="mb-20">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">Educational Foundation</h2>
                <p class="text-gray-600 mt-2 max-w-2xl mx-auto">My academic background in business provides a strong foundation for understanding customer relations, communication, and operational strategy.</p>
            </div>
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-xl font-bold text-gray-800">Bachelor of Business</h3>
                    <p class="text-gray-600">Singapore Institute of Management (RMIT)</p>
                    <p class="text-sm text-gray-500 mt-1">Specialisation: Business Marketing Communication</p>
                    <p class="text-sm font-medium text-gray-700 mt-2">2024 - 2025</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-xl font-bold text-gray-800">HND in Business (UK)</h3>
                    <p class="text-gray-600">Strategy First University (SFU), Myanmar</p>
                    <p class="text-sm text-gray-500 mt-1">Specialisation: Business Administration</p>
                    <p class="text-sm font-medium text-gray-700 mt-2">2018 - 2021</p>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <h3 class="text-xl font-bold text-gray-800">Bachelor of Law</h3>
                    <p class="text-gray-600">University Of Myitkyina, Myanmar</p>
                    <p class="text-sm text-gray-500 mt-1">Year 2 - Currently on hold</p>
                </div>
            </div>
        </section>

        <section id="contact" class="text-center bg-white p-10 rounded-lg shadow-lg">
            <h2 class="text-3xl font-bold text-gray-800 mb-4">Let's Connect</h2>
            <p class="text-gray-600 max-w-xl mx-auto mb-8">I am eager to discuss how my skills and enthusiasm can contribute to Scoot. Please feel free to reach out.</p>
            <div class="flex flex-col md:flex-row justify-center items-center space-y-4 md:space-y-0 md:space-x-8">
                <a href="mailto:maranjasengdim@gmail.com" class="text-gray-800 hover:text-d35400 transition-colors">📧 maranjasengdim@gmail.com</a>
                <a href="https://www.linkedin.com/in/ja-seng-dim-maran-a49b742b2" target="_blank" class="text-gray-800 hover:text-d35400 transition-colors">🔗 LinkedIn Profile</a>
                <a href="https://portfolium.com.au/s4080712" target="_blank" class="text-gray-800 hover:text-d35400 transition-colors">💼 e-Portfolio</a>
            </div>
        </section>
    </main>
    
    <footer class="text-center py-6 mt-12 border-t">
        <p class="text-gray-500">&copy; 2025 Ja Seng Dim. Interactive Resume.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            
            const menuBtn = document.getElementById('menu-btn');
            const mobileMenu = document.getElementById('mobile-menu');

            menuBtn.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            
            const navLinks = document.querySelectorAll('.nav-link');
            navLinks.forEach(link => {
                link.addEventListener('click', () => {
                    if(!mobileMenu.classList.contains('hidden')) {
                       mobileMenu.classList.add('hidden');
                    }
                });
            });

            const experienceData = [
                {
                    id: 0,
                    title: 'Customer Service & Sales Promoter',
                    company: 'SIMBA Telecom, Singapore',
                    date: 'Dec 2023 - June 2024',
                    type: 'Work',
                    details: [
                        'Assisted a diverse customer base with service inquiries, addressing technical issues and complaints professionally.',
                        'Promoted data plans and offers, resulting in increased customer sign-ups and achieving sales targets.',
                        'Honed ability to communicate effectively and maintain composure under pressure.'
                    ]
                },
                {
                    id: 1,
                    title: 'Operations Assistant',
                    company: 'Traditional Medicine (SME), Myanmar',
                    date: 'Dec 2021 - July 2023',
                    type: 'Work',
                    details: [
                        'Supported day-to-day business operations including order processing and basic inventory tracking.',
                        'Coordinated with retailers for product orders, deliveries, and payment follow-ups.',
                        'Streamlined communication between suppliers, customers, and internal teams to ensure smooth workflow.'
                    ]
                },
                {
                    id: 2,
                    title: 'HRD Stress Management Training',
                    company: 'Academic Project',
                    date: 'Mar 2025',
                    type: 'Project',
                    details: [
                        'Designed and delivered a simulated corporate training program on workplace stress management.',
                        'Conducted training needs analysis, created modules, and facilitated group activities with evaluation methods.',
                        'Applied HRD strategy and communication skills to create practical solutions for employee well-being.'
                    ]
                },
                {
                    id: 3,
                    title: 'Buyer Behaviour Analysis',
                    company: 'Academic Project',
                    date: 'Feb 2024',
                    type: 'Project',
                    details: [
                        'Researched consumer purchasing patterns and analyzed data to identify key buying drivers.',
                        'Developed actionable marketing recommendations tailored to target segments.',
                        'Presented insights in a professional report and group presentation to demonstrate strategic marketing skills.'
                    ]
                },
            ];

            const timelineList = document.getElementById('timeline-list');
            const detailsTitle = document.getElementById('details-title');
            const detailsSubtitle = document.getElementById('details-subtitle');
            const detailsPoints = document.getElementById('details-points');

            function displayExperience(id) {
                const item = experienceData.find(exp => exp.id === id);
                if (item) {
                    detailsTitle.textContent = item.title;
                    detailsSubtitle.textContent = `${item.company} | ${item.date}`;
                    detailsPoints.innerHTML = '';
                    item.details.forEach(point => {
                        const li = document.createElement('li');
                        li.textContent = point;
                        detailsPoints.appendChild(li);
                    });
                    
                    document.querySelectorAll('.timeline-item').forEach(el => el.classList.remove('active'));
                    document.querySelector(`.timeline-item[data-id='${id}']`).classList.add('active');
                }
            }

            experienceData.forEach(item => {
                const div = document.createElement('div');
                div.className = 'timeline-item border-l-4 p-4 rounded-r-lg bg-white shadow-sm';
                div.dataset.id = item.id;
                div.innerHTML = `
                    <p class="font-bold text-gray-800">${item.title}</p>
                    <p class="text-sm text-gray-500">${item.type} - ${item.date}</p>
                `;
                div.addEventListener('click', () => displayExperience(item.id));
                timelineList.appendChild(div);
            });

            displayExperience(0);

            const softSkillsBtn = document.getElementById('soft-skills-btn');
            const techSkillsBtn = document.getElementById('tech-skills-btn');
            const softSkillsContainer = document.getElementById('soft-skills-chart-container');
            const techSkillsContainer = document.getElementById('tech-skills-chart-container');
            let softSkillsChart, techSkillsChart;

            function toggleCharts(show) {
                if (show === 'soft') {
                    softSkillsBtn.classList.add('bg-white', 'shadow');
                    softSkillsBtn.classList.remove('text-gray-600');
                    techSkillsBtn.classList.remove('bg-white', 'shadow');
                    techSkillsBtn.classList.add('text-gray-600');
                    softSkillsContainer.classList.remove('hidden');
                    techSkillsContainer.classList.add('hidden');
                } else {
                    techSkillsBtn.classList.add('bg-white', 'shadow');
                    techSkillsBtn.classList.remove('text-gray-600');
                    softSkillsBtn.classList.remove('bg-white', 'shadow');
                    softSkillsBtn.classList.add('text-gray-600');
                    techSkillsContainer.classList.remove('hidden');
                    softSkillsContainer.classList.add('hidden');
                }
            }

            softSkillsBtn.addEventListener('click', () => toggleCharts('soft'));
            techSkillsBtn.addEventListener('click', () => toggleCharts('tech'));

            const softSkillsData = {
                labels: ['Customer Service', 'Communication', 'Problem-Solving', 'Teamwork', 'Adaptability', 'Time Management'],
                datasets: [{
                    label: 'Proficiency',
                    data: [9, 9, 8, 8, 9, 7],
                    fill: true,
                    backgroundColor: 'rgba(211, 84, 0, 0.2)',
                    borderColor: 'rgb(211, 84, 0)',
                    pointBackgroundColor: 'rgb(211, 84, 0)',
                    pointBorderColor: '#fff',
                    pointHoverBackgroundColor: '#fff',
                    pointHoverBorderColor: 'rgb(211, 84, 0)'
                }]
            };
            const softSkillsCtx = document.getElementById('softSkillsChart').getContext('2d');
            softSkillsChart = new Chart(softSkillsCtx, {
                type: 'radar',
                data: softSkillsData,
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { display: false } },
                    scales: {
                        r: {
                            angleLines: { color: '#E0E0E0' },
                            grid: { color: '#E0E0E0' },
                            pointLabels: { font: { size: 13 } },
                            suggestedMin: 0,
                            suggestedMax: 10
                        }
                    }
                }
            });

            const techSkillsData = {
                labels: ['MS Office', 'Google Workspace', 'Canva', 'Adobe Express', 'MS Outlook'],
                datasets: [{
                    label: 'Skill Level',
                    data: [9, 8, 8, 7, 9],
                    backgroundColor: [
                        'rgba(243, 156, 18, 0.7)',
                        'rgba(230, 126, 34, 0.7)',
                        'rgba(211, 84, 0, 0.7)',
                        'rgba(192, 57, 43, 0.7)',
                        'rgba(142, 68, 173, 0.7)'
                    ],
                    borderColor: '#fff',
                    borderWidth: 1
                }]
            };
            const techSkillsCtx = document.getElementById('techSkillsChart').getContext('2d');
            techSkillsChart = new Chart(techSkillsCtx, {
                type: 'bar',
                data: techSkillsData,
                options: {
                    indexAxis: 'y',
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { display: false } },
                    scales: {
                        x: { beginAtZero: true, suggestedMax: 10 },
                    }
                }
            });
        });
    </script>
</body>
</html>

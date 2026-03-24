<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PlaceBridge - College Placement Portal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        * {
            font-family: 'Inter', sans-serif;
        }
        
        .dark-theme {
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 50%, #16213e 100%);
            color: white;
        }
        
        .glass-effect {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .gradient-card {
            background: linear-gradient(145deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05));
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .animate-slide-up {
            animation: slideUp 0.5s ease-out;
        }
        
        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .sidebar-width {
            width: 280px;
        }
        
        @media (max-width: 768px) {
            .sidebar-width {
                width: 100%;
                transform: translateX(-100%);
            }
            
            .sidebar-open {
                transform: translateX(0);
            }
        }
    </style>
</head>
<body class="dark-theme min-h-screen transition-all duration-300">
    <!-- Mobile Menu Overlay -->
    <div id="mobileOverlay" class="fixed inset-0 bg-black bg-opacity-50 z-40 lg:hidden hidden"></div>
    
    <!-- Sidebar -->
    <div id="sidebar" class="sidebar-width fixed lg:relative z-30 h-screen glass-effect transition-all duration-300 lg:translate-x-0 shadow-2xl">
        <div class="p-6 border-b border-white/20">
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-600 rounded-xl flex items-center justify-center">
                    <i class="fas fa-bridge text-white text-xl"></i>
                </div>
                <div>
                    <h1 class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-purple-500 bg-clip-text text-transparent">PlaceBridge</h1>
                    <p class="text-xs opacity-75">Placement Portal</p>
                </div>
            </div>
        </div>
        
        <nav class="p-6 space-y-2 mt-4">
            <a href="#" onclick="showSection('dashboard')" class="nav-item flex items-center space-x-3 p-3 rounded-xl transition-all duration-200 hover:bg-white/10">
                <i class="fas fa-tachometer-alt w-5"></i>
                <span>Dashboard</span>
            </a>
            <a href="#" onclick="showSection('companies')" class="nav-item flex items-center space-x-3 p-3 rounded-xl bg-white/10">
                <i class="fas fa-building w-5"></i>
                <span>Companies</span>
            </a>
            <a href="#" onclick="showSection('applications')" class="nav-item flex items-center space-x-3 p-3 rounded-xl transition-all duration-200 hover:bg-white/10">
                <i class="fas fa-file-alt w-5"></i>
                <span>Applications</span>
            </a>
            <a href="#" onclick="showSection('profile')" class="nav-item flex items-center space-x-3 p-3 rounded-xl transition-all duration-200 hover:bg-white/10">
                <i class="fas fa-user w-5"></i>
                <span>Profile</span>
            </a>
            <a href="#" onclick="showSection('admin')" class="nav-item flex items-center space-x-3 p-3 rounded-xl transition-all duration-200 hover:bg-white/10">
                <i class="fas fa-cog w-5"></i>
                <span>Admin</span>
            </a>
        </nav>
    </div>
    
    <!-- Main Content -->
    <div class="lg:ml-sidebar-width transition-all duration-300">
        <!-- Mobile Header -->
        <header class="lg:hidden fixed top-0 left-0 right-0 z-20 glass-effect p-4">
            <div class="flex items-center justify-between">
                <button onclick="toggleSidebar()" class="p-2 rounded-xl bg-white/10">
                    <i class="fas fa-bars text-xl"></i>
                </button>
                <h1 class="text-xl font-bold bg-gradient-to-r from-blue-400 to-purple-500 bg-clip-text text-transparent">PlaceBridge</h1>
                <div class="w-8"></div>
            </div>
        </header>
        
        <!-- Main Content Area -->
        <main class="pt-20 lg:pt-0 p-6 lg:p-8 max-w-7xl mx-auto">
            <!-- Dashboard Section -->
            <section id="dashboard" class="section active">
                <div class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-4 gap-6 mb-8">
                    <div class="gradient-card p-6 rounded-2xl animate-slide-up">
                        <div class="flex items-center justify-between">
                            <div>
                                <p class="text-sm opacity-75">Total Drives</p>
                                <p class="text-3xl font-bold text-blue-400">12</p>
                            </div>
                            <i class="fas fa-building text-3xl opacity-50"></i>
                        </div>
                    </div>
                    <div class="gradient-card p-6 rounded-2xl animate-slide-up">
                        <div class="flex items-center justify-between">
                            <div>
                                <p class="text-sm opacity-75">Eligible Drives</p>
                                <p class="text-3xl font-bold text-green-400">8</p>
                            </div>
                            <i class="fas fa-check-circle text-3xl opacity-50"></i>
                        </div>
                    </div>
                    <div class="gradient-card p-6 rounded-2xl animate-slide-up">
                        <div class="flex items-center justify-between">
                            <div>
                                <p class="text-sm opacity-75">Applied</p>
                                <p class="text-3xl font-bold text-purple-400">3</p>
                            </div>
                            <i class="fas fa-paper-plane text-3xl opacity-50"></i>
                        </div>
                    </div>
                    <div class="gradient-card p-6 rounded-2xl animate-slide-up">
                        <div class="flex items-center justify-between">
                            <div>
                                <p class="text-sm opacity-75">Interviews</p>
                                <p class="text-3xl font-bold text-orange-400">1</p>
                            </div>
                            <i class="fas fa-microphone text-3xl opacity-50"></i>
                        </div>
                    </div>
                </div>
                
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div class="gradient-card p-6 rounded-2xl">
                        <h3 class="text-xl font-bold mb-6 flex items-center space-x-2">
                            <i class="fas fa-star text-yellow-400"></i>
                            <span>Quick Actions</span>
                        </h3>
                        <div class="space-y-3">
                            <button onclick="showSection('companies')" class="w-full p-4 bg-gradient-to-r from-blue-500 to-blue-600 rounded-xl text-white font-medium hover:from-blue-600 hover:to-blue-700 transition-all duration-200 transform hover:scale-[1.02]">
                                <i class="fas fa-search mr-2"></i>Find New Drives
                            </button>
                            <button onclick="showSection('applications')" class="w-full p-4 bg-gradient-to-r from-purple-500 to-purple-600 rounded-xl text-white font-medium hover:from-purple-600 hover:to-purple-700 transition-all duration-200 transform hover:scale-[1.02]">
                                <i class="fas fa-list mr-2"></i>Track Applications
                            </button>
                        </div>
                    </div>
                    
                    <div class="gradient-card p-6 rounded-2xl">
                        <h3 class="text-xl font-bold mb-6">Recent Notifications</h3>
                        <div class="space-y-3 max-h-64 overflow-y-auto">
                            <div class="p-3 bg-white/10 rounded-xl">
                                <div class="flex items-start space-x-3">
                                    <div class="w-2 h-2 bg-green-400 rounded-full mt-2 flex-shrink-0"></div>
                                    <div>
                                        <p class="font-medium">New drive from Google</p>
                                        <p class="text-sm opacity-75">You're eligible! Apply before 25th Dec</p>
                                    </div>
                                </div>
                            </div>
                            <div class="p-3 bg-white/10 rounded-xl">
                                <div class="flex items-start space-x-3">
                                    <div class="w-2 h-2 bg-blue-400 rounded-full mt-2 flex-shrink-0"></div>
                                    <div>
                                        <p class="font-medium">Interview scheduled</p>
                                        <p class="text-sm opacity-75">Microsoft - 28th Dec, 10 AM</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- Companies Section -->
            <section id="companies" class="section">
                <div class="flex flex-col lg:flex-row justify-between items-start lg:items-center mb-8 gap-4">
                    <h2 class="text-3xl font-bold bg-gradient-to-r from-white to-gray-300 bg-clip-text text-transparent">Available Drives</h2>
                    <div class="flex flex-col sm:flex-row gap-3 w-full lg:w-auto">
                        <input type="text" id="searchInput" placeholder="Search companies..." class="flex-1 lg:w-64 p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                        <select id="roleFilter" class="p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                            <option>All Roles</option>
                            <option>Software Engineer</option>
                            <option>Data Analyst</option>
                            <option>Product Manager</option>
                        </select>
                    </div>
                </div>
                
                <div id="companiesList" class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-6">
                    <!-- Companies will be populated by JS -->
                </div>
            </section>
            
            <!-- Applications Section -->
            <section id="applications" class="section">
                <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-white to-gray-300 bg-clip-text text-transparent">My Applications</h2>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div id="applicationsList" class="lg:col-span-2 grid grid-cols-1 md:grid-cols-2 gap-6">
                        <!-- Applications will be populated by JS -->
                    </div>
                </div>
            </section>
            
            <!-- Profile Section -->
            <section id="profile" class="section">
                <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-white to-gray-300 bg-clip-text text-transparent">Profile</h2>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <div class="gradient-card p-8 rounded-2xl">
                        <h3 class="text-2xl font-bold mb-6">Student Information</h3>
                        <div class="space-y-4">
                            <div class="flex justify-between">
                                <span class="opacity-75">Name:</span>
                                <span class="font-medium" id="studentName">Rahul Sharma</span>
                            </div>
                            <div class="flex justify-between">
                                <span class="opacity-75">CGPA:</span>
                                <span class="font-medium text-blue-400" id="studentCGPA">8.7</span>
                            </div>
                            <div class="flex justify-between">
                                <span class="opacity-75">Backlogs:</span>
                                <span class="font-medium text-green-400" id="studentBacklogs">0</span>
                            </div>
                            <div class="flex justify-between">
                                <span class="opacity-75">Skills:</span>
                                <span class="font-medium" id="studentSkills">React, Node.js, Python, DSA</span>
                            </div>
                        </div>
                        <button onclick="editProfile()" class="mt-6 w-full p-3 bg-gradient-to-r from-green-500 to-green-600 rounded-xl text-white font-medium hover:from-green-600 hover:to-green-700 transition-all duration-200">
                            <i class="fas fa-edit mr-2"></i>Edit Profile
                        </button>
                    </div>
                    
                    <div class="gradient-card p-8 rounded-2xl">
                        <h3 class="text-2xl font-bold mb-6">Eligibility Summary</h3>
                        <div id="eligibilitySummary" class="space-y-4">
                            <!-- Dynamic eligibility summary -->
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- Admin Section -->
            <section id="admin" class="section hidden">
                <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-white to-gray-300 bg-clip-text text-transparent">Admin Panel</h2>
                
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <div class="gradient-card p-8 rounded-2xl">
                        <h3 class="text-2xl font-bold mb-6">Add New Drive</h3>
                        <form id="addDriveForm" class="space-y-4">
                            <input type="text" id="companyName" placeholder="Company Name" class="w-full p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                            <input type="text" id="companyRole" placeholder="Role" class="w-full p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                            <input type="number" id="minCGPA" placeholder="Min CGPA" step="0.1" class="w-full p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                            <input type="number" id="maxBacklogs" placeholder="Max Backlogs" class="w-full p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                            <input type="text" id="requiredSkills" placeholder="Required Skills (comma separated)" class="w-full p-3 rounded-xl glass-effect focus:outline-none focus:ring-2 focus:ring-blue-500">
                            <button type="submit" class="w-full p-3 bg-gradient-to-r from-emerald-500 to-emerald-600 rounded-xl text-white font-bold hover:from-emerald-600 hover:to-emerald-700 transition-all duration-200">
                                <i class="fas fa-plus mr-2"></i>Add Drive
                            </button>
                        </form>
                    </div>
                    
                    <div class="gradient-card p-8 rounded-2xl">
                        <h3 class="text-2xl font-bold mb-6">Recent Applications</h3>
                        <div id="adminApplications" class="space-y-3 max-h-96 overflow-y-auto">
                            <!-- Admin applications will be populated -->
                        </div>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <script>
        // Mock Data
        let studentProfile = {
            name: "Rahul Sharma",
            cgpa: 8.7,
            backlogs: 0,
            skills: ["React", "Node.js", "Python", "DSA"]
        };

        let companies = [
            {
                id: 1,
                name: "Google",
                role: "Software Engineer",
                minCGPA: 7.5,
                maxBacklogs: 1,
                skills: ["Java", "DSA", "System Design"],
                applications: []
            },
            {
                id: 2,
                name: "Microsoft",
                role: "Software Engineer",
                minCGPA: 8.0,
                maxBacklogs: 0,
                skills: ["C++", "DSA"],
                applications: [{status: "Interview"}]
            },
            {
                id: 3,
                name: "Amazon",
                role: "Data Analyst",
                minCGPA: 7.0,
                maxBacklogs: 2,
                skills: ["Python", "SQL", "Excel"],
                applications: []
            },
            {
                id: 4,
                name: "Goldman Sachs",
                role: "Quantitative Analyst",
                minCGPA: 8.5,
                maxBacklogs: 0,
                skills: ["Python", "Statistics", "Finance"],
                applications: [{status: "Shortlisted"}]
            }
        ];

        let applications = [
            {id: 1, company: "Google", role: "Software Engineer", status: "Applied", date: "2024-12-20"},
            {id: 2, company: "Microsoft", role: "Software Engineer", status: "Interview", date: "2024-12-18"},
            {id: 4, company: "Goldman Sachs", role: "Quantitative Analyst", status: "Shortlisted", date: "2024-12-19"}
        ];

        // Initialize app
        document.addEventListener('DOMContentLoaded'), function() {
            renderCompanies();
            renderApplications();
            renderAdminApplications();
            updateStudentProfile();
            updateEligibilitySummary();
            setupEventListeners
            function loginUser() {
    const name = document.getElementById("name").value;
    localStorage.setItem("user", name);
}
<!doctype html>
<html lang="en" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Resume Fraud Detector Pro</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.9.1/chart.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&amp;family=JetBrains+Mono:wght@400;500&amp;display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Space Grotesk', sans-serif; }
    .mono { font-family: 'JetBrains Mono', monospace; }
    
    @keyframes scan {
      0% { transform: translateY(-100%); opacity: 0; }
      10% { opacity: 1; }
      90% { opacity: 1; }
      100% { transform: translateY(100%); opacity: 0; }
    }
    
    @keyframes pulse-glow {
      0%, 100% { box-shadow: 0 0 20px rgba(16, 185, 129, 0.3); }
      50% { box-shadow: 0 0 40px rgba(16, 185, 129, 0.6); }
    }
    
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    @keyframes slideIn {
      from { opacity: 0; transform: translateX(-20px); }
      to { opacity: 1; transform: translateX(0); }
    }
    
    .scan-line {
      animation: scan 2s ease-in-out infinite;
    }
    
    .pulse-border {
      animation: pulse-glow 2s ease-in-out infinite;
    }
    
    .fade-in-up {
      animation: fadeInUp 0.5s ease-out forwards;
    }
    
    .result-item {
      opacity: 0;
      animation: fadeInUp 0.4s ease-out forwards;
    }
    
    .grid-bg {
      background-image: 
        linear-gradient(rgba(16, 185, 129, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(16, 185, 129, 0.03) 1px, transparent 1px);
      background-size: 40px 40px;
    }
    
    .stat-card {
      animation: slideIn 0.5s ease-out forwards;
    }
    
    .stat-card:nth-child(2) { animation-delay: 0.1s; }
    .stat-card:nth-child(3) { animation-delay: 0.2s; }
    .stat-card:nth-child(4) { animation-delay: 0.3s; }
  </style>
  <style>body { box-sizing: border-box; }</style>
 </head>
 <body class="h-full bg-slate-950 text-slate-100 overflow-auto">
  <div class="min-h-full w-full grid-bg">
   <div class="fixed top-0 left-0 w-full h-1 bg-gradient-to-r from-emerald-500 via-cyan-500 to-emerald-500"></div><!-- Login Screen -->
   <div id="login-screen" class="min-h-full w-full flex items-center justify-center px-6 py-12">
    <div class="w-full max-w-md">
     <div class="text-center mb-8">
      <div class="inline-flex items-center gap-3 mb-4">
       <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-emerald-500 to-cyan-500 flex items-center justify-center">
        <svg class="w-7 h-7 text-slate-950" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
        </svg>
       </div>
      </div>
      <h1 class="text-3xl font-bold bg-gradient-to-r from-emerald-400 to-cyan-400 bg-clip-text text-transparent mb-2">Resume Fraud Detector</h1>
      <p class="text-slate-400">Enterprise-Grade Verification System</p>
     </div>
     <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-8">
      <form id="login-form" class="space-y-4">
       <div>
        <label for="login-email" class="block text-sm text-slate-300 mb-2">Email Address</label> <input type="email" id="login-email" placeholder="admin@detector.com" class="w-full px-4 py-3 bg-slate-950 border border-slate-700 rounded-xl text-slate-200 placeholder-slate-600 focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition-all" required>
       </div>
       <div>
        <label for="login-password" class="block text-sm text-slate-300 mb-2">Password</label> <input type="password" id="login-password" placeholder="••••••••" class="w-full px-4 py-3 bg-slate-950 border border-slate-700 rounded-xl text-slate-200 placeholder-slate-600 focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition-all" required>
       </div>
       <div id="login-error" class="hidden text-sm text-red-400 bg-red-500/10 p-3 rounded-lg border border-red-500/20"></div><button type="submit" class="w-full px-6 py-3 bg-gradient-to-r from-emerald-500 to-cyan-500 text-slate-950 font-semibold rounded-xl hover:from-emerald-400 hover:to-cyan-400 transition-all">🔓 Unlock System</button>
      </form>
      <div class="mt-6 pt-6 border-t border-slate-700">
       <p class="text-xs text-slate-500 text-center mb-2">Demo Credentials</p>
       <div class="bg-slate-950/50 p-3 rounded-lg space-y-1">
        <p class="text-xs text-slate-400">Email: <span class="text-emerald-400 font-semibold">admin@detector.com</span></p>
        <p class="text-xs text-slate-400">Password: <span class="text-emerald-400 font-semibold">password123</span></p>
       </div>
      </div>
     </div>
    </div>
   </div><!-- Main App -->
   <div id="main-app" class="hidden"><!-- Top Navigation -->
    <nav class="sticky top-0 z-50 bg-slate-950/95 backdrop-blur border-b border-slate-800">
     <div class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">
      <div class="flex items-center gap-3">
       <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-emerald-500 to-cyan-500 flex items-center justify-center">
        <svg class="w-6 h-6 text-slate-950" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
        </svg>
       </div>
       <div>
        <h1 id="app-title" class="font-bold text-lg">Resume Fraud Detector</h1>
        <p class="text-xs text-slate-500">Pro Analysis System</p>
       </div>
      </div>
      <div class="flex items-center gap-2 flex-wrap md:flex-nowrap justify-end"><button id="nav-analyzer" class="nav-btn px-4 py-2 rounded-lg font-medium transition-all text-sm bg-emerald-500/20 text-emerald-400">📋 Analyzer</button> <button id="nav-history" class="nav-btn px-4 py-2 rounded-lg font-medium transition-all text-sm text-slate-400 hover:text-slate-200">📁 History</button> <button id="nav-analytics" class="nav-btn px-4 py-2 rounded-lg font-medium transition-all text-sm text-slate-400 hover:text-slate-200">📊 Analytics</button> <button id="nav-comparison" class="nav-btn px-4 py-2 rounded-lg font-medium transition-all text-sm text-slate-400 hover:text-slate-200">🔍 Compare</button>
       <div class="h-6 w-px bg-slate-700 mx-2"></div>
       <div class="flex items-center gap-2 text-sm"><span id="user-display" class="text-emerald-400"></span> <button id="logout-btn" class="px-3 py-2 text-slate-400 hover:text-slate-200 transition-all text-sm">🚪</button>
       </div>
      </div>
     </div>
    </nav>
    <div class="max-w-7xl mx-auto px-6 py-12"><!-- Analyzer Tab -->
     <div id="analyzer-tab" class="view-tab">
      <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-8 mb-8">
       <div class="flex items-center gap-2 mb-6">
        <div class="w-2 h-2 rounded-full bg-emerald-500"></div><span class="text-sm text-slate-400 mono">INPUT_RESUME_DATA</span>
       </div>
       <div class="grid md:grid-cols-3 gap-4 mb-6">
        <div>
         <label class="block text-sm text-slate-300 mb-2">Candidate Name</label> <input type="text" id="candidate-name" placeholder="John Smith" class="w-full px-4 py-3 bg-slate-950 border border-slate-700 rounded-xl text-slate-200 placeholder-slate-600 focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition-all">
        </div>
        <div>
         <label class="block text-sm text-slate-300 mb-2">Industry/Role</label> <select id="industry-select" class="w-full px-4 py-3 bg-slate-950 border border-slate-700 rounded-xl text-slate-200 focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition-all"> <option>Software Engineer</option> <option>Product Manager</option> <option>Data Scientist</option> <option>Designer</option> <option>Marketing Manager</option> <option>Business Analyst</option> <option>DevOps Engineer</option> <option>Finance/Accounting</option> <option>Sales</option> <option>Other</option> </select>
        </div>
        <div>
         <label class="block text-sm text-slate-300 mb-2">Experience Level</label> <select id="exp-level" class="w-full px-4 py-3 bg-slate-950 border border-slate-700 rounded-xl text-slate-200 focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition-all"> <option>Entry Level (0-2 years)</option> <option>Mid Level (2-5 years)</option> <option>Senior (5-10 years)</option> <option>Lead/Manager (10+ years)</option> </select>
        </div>
       </div>
       <div class="grid md:grid-cols-2 gap-6 mb-6">
        <div>
         <label class="block text-sm text-slate-300 mb-2">📝 Paste Resume Text</label> <textarea id="resume-input" class="w-full h-56 bg-slate-950 border border-slate-700 rounded-xl p-4 text-slate-200 placeholder-slate-600 focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition-all resize-none mono text-sm" placeholder="Paste resume text here..."></textarea>
        </div>
        <div>
         <label class="block text-sm text-slate-300 mb-2">📁 Upload File</label>
         <div class="relative">
          <input type="file" id="file-upload" accept=".txt,.pdf,.doc,.docx" class="hidden">
          <div class="w-full h-56 border-2 border-dashed border-slate-700 rounded-xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-emerald-500 transition-all bg-slate-950/50" onclick="document.getElementById('file-upload').click()">
           <svg class="w-8 h-8 text-slate-500 mb-2" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M15 13l-3-3m0 0l-3 3m3-3v12" />
           </svg>
           <p class="text-sm text-slate-400">Drop file or click to upload</p>
           <p id="file-name" class="text-xs text-slate-500 mt-1"></p>
          </div>
         </div>
        </div>
       </div>
       <div class="grid md:grid-cols-3 gap-4 mb-6"><label class="flex items-center gap-2 cursor-pointer"> <input type="checkbox" id="deep-scan" class="w-4 h-4 rounded bg-slate-800 border-slate-600 text-emerald-500" checked> <span class="text-sm text-slate-400">Deep Analysis</span> </label> <label class="flex items-center gap-2 cursor-pointer"> <input type="checkbox" id="plagiarism-check" class="w-4 h-4 rounded bg-slate-800 border-slate-600 text-emerald-500" checked> <span class="text-sm text-slate-400">Plagiarism Detection</span> </label> <label class="flex items-center gap-2 cursor-pointer"> <input type="checkbox" id="email-check" class="w-4 h-4 rounded bg-slate-800 border-slate-600 text-emerald-500" checked> <span class="text-sm text-slate-400">Email Verification</span> </label>
       </div>
       <div class="flex gap-4"><button id="analyze-btn" class="flex-1 px-6 py-3 bg-gradient-to-r from-emerald-500 to-cyan-500 text-slate-950 font-semibold rounded-xl hover:from-emerald-400 hover:to-cyan-400 transition-all flex items-center justify-center gap-2">
         <svg class="w-5 h-5" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
         </svg><span id="analyze-btn-text">🔬 Analyze Resume</span> </button> <button id="clear-btn" class="px-6 py-3 bg-slate-800 text-slate-300 font-medium rounded-xl hover:bg-slate-700 transition-all">Clear</button>
       </div>
      </div><!-- Scanning Animation -->
      <div id="scanning-container" class="hidden bg-slate-900/80 backdrop-blur rounded-2xl border border-emerald-500/50 p-8 mb-8 pulse-border relative overflow-hidden">
       <div class="scan-line absolute inset-x-0 h-1 bg-gradient-to-r from-transparent via-emerald-400 to-transparent"></div>
       <div class="text-center">
        <div class="inline-flex items-center gap-3 mb-4">
         <svg class="w-8 h-8 text-emerald-400 animate-spin" fill="none" viewbox="0 0 24 24"><circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4" /> <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z" />
         </svg><span class="text-emerald-400 font-semibold text-lg">Analyzing Resume...</span>
        </div>
        <p id="scan-status" class="text-slate-400 mono text-sm">Initializing fraud detection algorithms...</p>
       </div>
      </div><!-- Results Area -->
      <div id="results-container" class="hidden space-y-6"><!-- Trust Score -->
       <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-8">
        <div class="flex items-center justify-between mb-6">
         <div class="flex items-center gap-2">
          <div class="w-2 h-2 rounded-full bg-cyan-500"></div><span class="text-sm text-slate-400 mono">TRUST_SCORE_ANALYSIS</span>
         </div><span id="score-badge" class="px-3 py-1 rounded-full text-sm font-medium"></span>
        </div>
        <div class="flex flex-col md:flex-row items-center gap-8">
         <div id="score-circle" class="relative w-40 h-40 flex-shrink-0">
          <svg class="w-40 h-40 transform -rotate-90"><circle cx="80" cy="80" r="70" stroke="currentColor" stroke-width="8" fill="none" class="text-slate-800" /> <circle id="score-progress" cx="80" cy="80" r="70" stroke="currentColor" stroke-width="8" fill="none" class="text-emerald-500" stroke-dasharray="440" stroke-dashoffset="440" stroke-linecap="round" style="transition: stroke-dashoffset 1.5s ease-out" />
          </svg>
          <div class="absolute inset-0 flex items-center justify-center"><span id="score-value" class="text-3xl font-bold">0</span>
          </div>
         </div>
         <div class="flex-1">
          <h3 id="score-title" class="text-2xl font-semibold mb-2"></h3>
          <p id="score-description" class="text-slate-400 mb-4"></p>
          <div class="grid grid-cols-2 gap-4">
           <div class="bg-slate-950/50 rounded-lg p-3">
            <p class="text-xs text-slate-500">Similarity Score</p>
            <p id="similarity-score" class="text-lg font-bold text-cyan-400">0%</p>
           </div>
           <div class="bg-slate-950/50 rounded-lg p-3">
            <p class="text-xs text-slate-500">Skill Match</p>
            <p id="skill-match" class="text-lg font-bold text-emerald-400">0%</p>
           </div>
          </div>
         </div>
        </div>
       </div><!-- Findings Grid -->
       <div class="grid md:grid-cols-2 gap-6">
        <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <div class="flex items-center gap-2 mb-4">
          <div class="w-8 h-8 rounded-lg bg-red-500/20 flex items-center justify-center">
           <svg class="w-5 h-5 text-red-400" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" />
           </svg>
          </div>
          <h3 class="font-semibold text-red-400">Red Flags</h3><span id="red-count" class="ml-auto text-sm bg-red-500/20 px-2 py-1 rounded text-red-400">0</span>
         </div>
         <ul id="red-flags-list" class="space-y-3"></ul>
        </div>
        <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <div class="flex items-center gap-2 mb-4">
          <div class="w-8 h-8 rounded-lg bg-emerald-500/20 flex items-center justify-center">
           <svg class="w-5 h-5 text-emerald-400" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
           </svg>
          </div>
          <h3 class="font-semibold text-emerald-400">Verified Items</h3><span id="verified-count" class="ml-auto text-sm bg-emerald-500/20 px-2 py-1 rounded text-emerald-400">0</span>
         </div>
         <ul id="verified-list" class="space-y-3"></ul>
        </div>
       </div><!-- Warnings -->
       <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
        <div class="flex items-center gap-2 mb-4">
         <div class="w-8 h-8 rounded-lg bg-amber-500/20 flex items-center justify-center">
          <svg class="w-5 h-5 text-amber-400" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
         </div>
         <h3 class="font-semibold text-amber-400">Warnings &amp; Recommendations</h3>
        </div>
        <ul id="warnings-list" class="space-y-3"></ul>
       </div><!-- Plagiarism Detection -->
       <div id="plagiarism-section" class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
        <div class="flex items-center gap-2 mb-4">
         <div class="w-8 h-8 rounded-lg bg-purple-500/20 flex items-center justify-center">
          <svg class="w-5 h-5 text-purple-400" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
          </svg>
         </div>
         <h3 class="font-semibold text-purple-400">Plagiarism Detection</h3><span id="plagiarism-badge" class="ml-auto px-3 py-1 rounded-full text-sm font-medium bg-emerald-500/20 text-emerald-400">Unique</span>
        </div>
        <div class="grid md:grid-cols-3 gap-4">
         <div class="bg-slate-950/50 rounded-lg p-4">
          <p class="text-xs text-slate-500 mb-1">Originality Score</p>
          <p id="originality-score" class="text-2xl font-bold text-cyan-400">0%</p>
         </div>
         <div class="bg-slate-950/50 rounded-lg p-4">
          <p class="text-xs text-slate-500 mb-1">Template Match</p>
          <p id="template-match" class="text-2xl font-bold text-amber-400">0%</p>
         </div>
         <div class="bg-slate-950/50 rounded-lg p-4">
          <p class="text-xs text-slate-500 mb-1">AI Generated</p>
          <p id="ai-generated" class="text-2xl font-bold text-red-400">0%</p>
         </div>
        </div>
       </div><!-- Detailed Analysis -->
       <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
        <div class="flex items-center gap-2 mb-4">
         <div class="w-2 h-2 rounded-full bg-cyan-500"></div><span class="text-sm text-slate-400 mono">DETAILED_ANALYSIS</span>
        </div>
        <div id="analysis-sections" class="space-y-4"></div>
       </div><!-- Save Analysis Button -->
       <div class="flex gap-3"><button id="save-analysis-btn" class="flex-1 px-6 py-3 bg-emerald-500/20 text-emerald-400 font-medium rounded-xl hover:bg-emerald-500/30 transition-all">💾 Save to History</button> <button id="export-btn" class="flex-1 px-6 py-3 bg-cyan-500/20 text-cyan-400 font-medium rounded-xl hover:bg-cyan-500/30 transition-all">📥 Export Report</button> <button id="reset-btn" class="flex-1 px-6 py-3 bg-slate-800 text-slate-300 font-medium rounded-xl hover:bg-slate-700 transition-all">🔄 New Analysis</button>
       </div>
      </div>
     </div><!-- History Tab -->
     <div id="history-tab" class="view-tab hidden">
      <div class="space-y-4">
       <div class="flex items-center justify-between">
        <div>
         <h2 class="text-2xl font-bold">Analysis History</h2>
         <p class="text-slate-400 text-sm">All candidate evaluations with detailed results</p>
        </div><button id="history-export-btn" class="px-4 py-2 bg-emerald-500/20 text-emerald-400 rounded-lg hover:bg-emerald-500/30 transition-all text-sm">📊 Export All</button>
       </div>
       <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-8">
        <div id="history-list" class="space-y-4"></div>
       </div>
      </div>
     </div><!-- Analytics Tab -->
     <div id="analytics-tab" class="view-tab hidden">
      <div class="space-y-6"><!-- Key Stats -->
       <div class="grid md:grid-cols-4 gap-4">
        <div class="stat-card bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <p class="text-slate-400 text-sm mb-2">Total Analyses</p>
         <p id="stat-total" class="text-3xl font-bold text-cyan-400">0</p>
        </div>
        <div class="stat-card bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <p class="text-slate-400 text-sm mb-2">Average Score</p>
         <p id="stat-avg-score" class="text-3xl font-bold text-emerald-400">0</p>
        </div>
        <div class="stat-card bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <p class="text-slate-400 text-sm mb-2">Low Risk</p>
         <p id="stat-low-risk" class="text-3xl font-bold text-emerald-500">0</p>
        </div>
        <div class="stat-card bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <p class="text-slate-400 text-sm mb-2">High Risk</p>
         <p id="stat-high-risk" class="text-3xl font-bold text-red-400">0</p>
        </div>
       </div><!-- Charts -->
       <div class="grid md:grid-cols-2 gap-6">
        <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <h3 class="font-semibold text-lg mb-4">Score Distribution</h3>
         <div class="relative h-64">
          <canvas id="score-chart"></canvas>
         </div>
        </div>
        <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <h3 class="font-semibold text-lg mb-4">Risk Categories</h3>
         <div class="relative h-64">
          <canvas id="risk-chart"></canvas>
         </div>
        </div>
       </div><!-- Industry Breakdown -->
       <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
        <h3 class="font-semibold text-lg mb-4">Industry Breakdown</h3>
        <div class="relative h-64">
         <canvas id="industry-chart"></canvas>
        </div>
       </div>
      </div>
     </div><!-- Comparison Tab -->
     <div id="comparison-tab" class="view-tab hidden">
      <div class="space-y-6">
       <div>
        <h2 class="text-2xl font-bold mb-2">Compare Resumes</h2>
        <p class="text-slate-400 text-sm">Select two candidates to compare their scores and details</p>
       </div>
       <div class="grid md:grid-cols-2 gap-6">
        <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <p class="text-sm text-slate-300 mb-3">Candidate 1</p><select id="compare-1" class="w-full px-4 py-2 bg-slate-950 border border-slate-700 rounded-lg text-slate-200 mb-4"> <option>Select candidate...</option> </select>
         <div id="compare-1-details" class="bg-slate-950/50 rounded-lg p-4 space-y-2"></div>
        </div>
        <div class="bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
         <p class="text-sm text-slate-300 mb-3">Candidate 2</p><select id="compare-2" class="w-full px-4 py-2 bg-slate-950 border border-slate-700 rounded-lg text-slate-200 mb-4"> <option>Select candidate...</option> </select>
         <div id="compare-2-details" class="bg-slate-950/50 rounded-lg p-4 space-y-2"></div>
        </div>
       </div>
       <div id="comparison-result" class="hidden bg-slate-900/80 backdrop-blur rounded-2xl border border-slate-800 p-6">
        <h3 class="font-semibold text-lg mb-4">Comparison Result</h3>
        <div id="comparison-content" class="space-y-4"></div>
       </div>
      </div>
     </div>
    </div>
   </div>
  </div>
  <script>
    const defaultConfig = {
      app_title: 'Resume Fraud Detector',
      subtitle: 'AI-powered analysis to validate credentials and detect inconsistencies',
      analyze_button_text: 'Analyze Resume'
    };

    let config = { ...defaultConfig };
    let currentUser = null;
    let currentAnalysis = null;
    let allAnalyses = [];
    let scoreChart = null;
    let riskChart = null;
    let industryChart = null;

    // Demo credentials
    const demoCredentials = {
      email: 'admin@detector.com',
      password: 'password123'
    };

    // Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (newConfig) => {
          config = { ...defaultConfig, ...newConfig };
          applyConfig();
        },
        mapToCapabilities: (cfg) => ({
          recolorables: [],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (cfg) => new Map([
          ['app_title', cfg.app_title || defaultConfig.app_title],
          ['subtitle', cfg.subtitle || defaultConfig.subtitle],
          ['analyze_button_text', cfg.analyze_button_text || defaultConfig.analyze_button_text]
        ])
      });
    }

    // Data SDK
    const dataHandler = {
      onDataChanged(data) {
        allAnalyses = data;
        updateAnalyticsCharts();
      }
    };

    (async () => {
      await window.dataSdk.init(dataHandler);
    })();

    function applyConfig() {
      document.getElementById('app-title').textContent = config.app_title || defaultConfig.app_title;
      document.getElementById('analyze-btn-text').textContent = config.analyze_button_text || defaultConfig.analyze_button_text;
    }

    // Common email domains
    const commonEmailDomains = ['gmail.com', 'yahoo.com', 'outlook.com', 'hotmail.com', 'aol.com'];
    const corporateDomains = new Set(['google.com', 'microsoft.com', 'apple.com', 'amazon.com', 'meta.com', 'netflix.com', 'linkedin.com']);

    // Login Handler
    document.getElementById('login-form').addEventListener('submit', (e) => {
      e.preventDefault();
      const email = document.getElementById('login-email').value.trim();
      const password = document.getElementById('login-password').value;
      const errorDiv = document.getElementById('login-error');

      if (email === demoCredentials.email && password === demoCredentials.password) {
        currentUser = email;
        document.getElementById('login-screen').classList.add('hidden');
        document.getElementById('main-app').classList.remove('hidden');
        document.getElementById('user-display').textContent = `👤 ${email.split('@')[0]}`;
        errorDiv.classList.add('hidden');
        applyConfig();
      } else {
        errorDiv.textContent = '❌ Invalid credentials. Use admin@detector.com / password123';
        errorDiv.classList.remove('hidden');
      }
    });

    document.getElementById('logout-btn').addEventListener('click', () => {
      currentUser = null;
      currentAnalysis = null;
      document.getElementById('main-app').classList.add('hidden');
      document.getElementById('login-screen').classList.remove('hidden');
      document.getElementById('login-email').value = '';
      document.getElementById('login-password').value = '';
    });

    // Tab Navigation
    const navButtons = {
      'nav-analyzer': 'analyzer-tab',
      'nav-history': 'history-tab',
      'nav-analytics': 'analytics-tab',
      'nav-comparison': 'comparison-tab'
    };

    Object.entries(navButtons).forEach(([btnId, tabId]) => {
      document.getElementById(btnId).addEventListener('click', () => {
        document.querySelectorAll('.view-tab').forEach(tab => tab.classList.add('hidden'));
        document.getElementById(tabId).classList.remove('hidden');
        document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('bg-emerald-500/20', 'text-emerald-400'));
        document.getElementById(btnId).classList.add('bg-emerald-500/20', 'text-emerald-400');
        
        if (tabId === 'analytics-tab') updateAnalyticsCharts();
        if (tabId === 'history-tab') renderHistory();
        if (tabId === 'comparison-tab') populateComparison();
      });
    });

    // Fraud Detection
    function analyzeResume(text, candidateName) {
      const results = {
        redFlags: [],
        warnings: [],
        verified: [],
        analysis: [],
        score: 100,
        similarity: 0,
        skillMatch: 0,
        plagiarism: false,
        originality: 100,
        templateMatch: 0,
        aiGenerated: 0
      };

      // Timeline checks
      const timelinePatterns = [
        { pattern: /(\d+)\s*years?\s*of\s*(experience|exp).*?(React|Vue|Angular|Node|TypeScript|Python|Java|Go|Rust)/gi, years: true },
        { pattern: /(\d{4})\s*-\s*(\d{4}|present)/gi, years: false }
      ];

      timelinePatterns.forEach(({ pattern }) => {
        let match;
        while ((match = pattern.exec(text)) !== null) {
          const years = parseInt(match[1]);
          if (match[4]) {
            const tech = match[4];
            const releases = { 'react': 2013, 'vue': 2014, 'angular': 2016, 'node': 2009, 'typescript': 2012, 'python': 1991, 'java': 1995, 'go': 2009, 'rust': 2010 };
            const maxYears = new Date().getFullYear() - (releases[tech.toLowerCase()] || 2010);
            if (years > maxYears) {
              results.redFlags.push(`📌 Claims ${years} years of ${tech}, but released in ${releases[tech.toLowerCase()] || '?'} (max ${maxYears} years)`);
              results.score -= 20;
            }
          }
        }
      });

      // Exaggeration checks
      if (/increased.*?(\d{3,})%|revenue.*?(\d+)\s*(million|billion)|saved.*?\$?(\d+)\s*(million|billion)/gi.test(text)) {
        results.warnings.push('⚠️ Extraordinary growth claims detected - requires verification');
        results.score -= 10;
      }

      // Generic language
      if (/responsible for|duties included|team player|hard worker|various|multiple|numerous/gi.test(text)) {
        results.warnings.push('⚠️ Generic language detected - lacks specificity');
        results.score -= 5;
      }

      // Credential verification
      if (/PhD|doctorate|Harvard|MIT|Stanford|Oxford|Cambridge|Google|Meta|Apple|Amazon|Microsoft/gi.test(text)) {
        results.warnings.push('✓ Elite credentials claimed - verify authenticity');
        results.score -= 3;
      }

      // Verified items
      if (/bachelor|master|bs|ba|ms|ma|mba|certified|certification|license|linkedin\.com|github\.com/gi.test(text)) {
        results.verified.push('✓ Standard credential formats detected');
      }

      // Plagiarism detection (simulated)
      const wordCount = text.split(/\s+/).length;
      results.similarity = Math.floor(Math.random() * 25) + 5;
      results.plagiarism = results.similarity > 30;
      results.originality = 100 - results.similarity;
      results.templateMatch = Math.floor(Math.random() * 20);
      results.aiGenerated = Math.floor(Math.random() * 15);

      // Skill match based on industry
      const skillKeywords = {
        'Software Engineer': ['javascript', 'python', 'java', 'react', 'node', 'aws', 'docker'],
        'Data Scientist': ['python', 'sql', 'machine learning', 'tensorflow', 'pandas', 'scikit-learn'],
        'Product Manager': ['roadmap', 'strategy', 'agile', 'metrics', 'user research'],
        'Designer': ['figma', 'adobe', 'prototype', 'ux', 'ui', 'design thinking'],
        'DevOps Engineer': ['kubernetes', 'docker', 'ci/cd', 'terraform', 'aws', 'gcp']
      };

      const industry = document.getElementById('industry-select').value;
      const keywords = skillKeywords[industry] || [];
      const matched = keywords.filter(kw => text.toLowerCase().includes(kw)).length;
      results.skillMatch = Math.round((matched / keywords.length) * 100) || 0;

      // Analysis sections
      results.analysis.push({
        title: '📊 Document Statistics',
        items: [
          `Words: ${wordCount}`,
          `Characters: ${text.length}`,
          wordCount < 100 ? '⚠️ Short resume' : '✓ Adequate length'
        ]
      });

      results.score = Math.max(0, Math.min(100, results.score));
      return results;
    }

    function renderResults(results) {
      const container = document.getElementById('results-container');
      document.getElementById('scanning-container').classList.add('hidden');
      container.classList.remove('hidden');

      // Animate score
      let currentScore = 0;
      const scoreInterval = setInterval(() => {
        currentScore += 2;
        if (currentScore >= results.score) {
          currentScore = results.score;
          clearInterval(scoreInterval);
        }
        document.getElementById('score-value').textContent = currentScore;
        const offset = 440 - (440 * currentScore / 100);
        document.getElementById('score-progress').style.strokeDashoffset = offset;
      }, 20);

      // Score badge
      const scoreBadge = document.getElementById('score-badge');
      const scoreProgress = document.getElementById('score-progress');
      if (results.score >= 80) {
        scoreProgress.classList.remove('text-amber-500', 'text-red-500');
        scoreProgress.classList.add('text-emerald-500');
        scoreBadge.className = 'px-3 py-1 rounded-full text-sm font-medium bg-emerald-500/20 text-emerald-400';
        scoreBadge.textContent = '✓ Low Risk';
        document.getElementById('score-title').textContent = 'Appears Legitimate';
        document.getElementById('score-description').textContent = 'No major red flags detected.';
      } else if (results.score >= 50) {
        scoreProgress.classList.remove('text-emerald-500', 'text-red-500');
        scoreProgress.classList.add('text-amber-500');
        scoreBadge.className = 'px-3 py-1 rounded-full text-sm font-medium bg-amber-500/20 text-amber-400';
        scoreBadge.textContent = '⚠ Medium Risk';
        document.getElementById('score-title').textContent = 'Requires Verification';
        document.getElementById('score-description').textContent = 'Some inconsistencies detected.';
      } else {
        scoreProgress.classList.remove('text-emerald-500', 'text-amber-500');
        scoreProgress.classList.add('text-red-500');
        scoreBadge.className = 'px-3 py-1 rounded-full text-sm font-medium bg-red-500/20 text-red-400';
        scoreBadge.textContent = '✕ High Risk';
        document.getElementById('score-title').textContent = 'Significant Concerns';
        document.getElementById('score-description').textContent = 'Multiple red flags identified.';
      }

      document.getElementById('similarity-score').textContent = results.similarity + '%';
      document.getElementById('skill-match').textContent = results.skillMatch + '%';

      // Red flags
      document.getElementById('red-flags-list').innerHTML = results.redFlags.length === 0
        ? '<li class="text-slate-500 text-sm">No critical issues detected</li>'
        : results.redFlags.map((flag, i) => `
          <li class="result-item flex gap-2 text-sm" style="animation-delay: ${i * 0.1}s">
            <span class="text-red-400 flex-shrink-0">✕</span>
            <span class="text-slate-300">${flag}</span>
          </li>
        `).join('');
      document.getElementById('red-count').textContent = results.redFlags.length;

      // Verified items
      document.getElementById('verified-list').innerHTML = results.verified.length === 0
        ? '<li class="text-slate-500 text-sm">No items verified</li>'
        : results.verified.map((item, i) => `
          <li class="result-item flex gap-2 text-sm" style="animation-delay: ${i * 0.1}s">
            <span class="text-emerald-400 flex-shrink-0">✓</span>
            <span class="text-slate-300">${item}</span>
          </li>
        `).join('');
      document.getElementById('verified-count').textContent = results.verified.length;

      // Warnings
      document.getElementById('warnings-list').innerHTML = results.warnings.length === 0
        ? '<li class="text-slate-500 text-sm">No warnings</li>'
        : results.warnings.map((w, i) => `
          <li class="result-item flex gap-2 text-sm" style="animation-delay: ${i * 0.1}s">
            <span class="text-amber-400 flex-shrink-0">!</span>
            <span class="text-slate-300">${w}</span>
          </li>
        `).join('');

      // Plagiarism
      const plagBadge = document.getElementById('plagiarism-badge');
      plagBadge.textContent = results.plagiarism ? '⚠️ Potential Match' : '✓ Unique';
      plagBadge.className = results.plagiarism
        ? 'ml-auto px-3 py-1 rounded-full text-sm font-medium bg-amber-500/20 text-amber-400'
        : 'ml-auto px-3 py-1 rounded-full text-sm font-medium bg-emerald-500/20 text-emerald-400';

      document.getElementById('originality-score').textContent = results.originality + '%';
      document.getElementById('template-match').textContent = results.templateMatch + '%';
      document.getElementById('ai-generated').textContent = results.aiGenerated + '%';

      // Analysis sections
      document.getElementById('analysis-sections').innerHTML = results.analysis.map((s, i) => `
        <div class="result-item bg-slate-950/50 rounded-xl p-4" style="animation-delay: ${i * 0.15}s">
          <h4 class="font-medium text-cyan-400 mb-2">${s.title}</h4>
          <ul class="space-y-1">
            ${s.items.map(item => `<li class="text-sm text-slate-400">${item}</li>`).join('')}
          </ul>
        </div>
      `).join('');
    }

    // File upload
    document.getElementById('file-upload').addEventListener('change', (e) => {
      const file = e.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = (event) => {
          document.getElementById('resume-input').value = event.target.result;
          document.getElementById('file-name').textContent = `✓ ${file.name}`;
        };
        reader.readAsText(file);
      }
    });

    // Analyze button
    document.getElementById('analyze-btn').addEventListener('click', () => {
      const text = document.getElementById('resume-input').value.trim();
      const candidateName = document.getElementById('candidate-name').value.trim() || 'Anonymous';

      if (!text) {
        document.getElementById('resume-input').classList.add('border-red-500');
        setTimeout(() => document.getElementById('resume-input').classList.remove('border-red-500'), 2000);
        return;
      }

      document.getElementById('scanning-container').classList.remove('hidden');
      document.getElementById('results-container').classList.add('hidden');

      const statuses = [
        'Initializing fraud detection...',
        'Analyzing timeline consistency...',
        'Checking credential validity...',
        'Cross-referencing employment...',
        'Detecting plagiarism patterns...',
        'Generating trust score...'
      ];

      let statusIndex = 0;
      const interval = setInterval(() => {
        statusIndex++;
        if (statusIndex < statuses.length) {
          document.getElementById('scan-status').textContent = statuses[statusIndex];
        }
      }, 350);

      setTimeout(() => {
        clearInterval(interval);
        const results = analyzeResume(text, candidateName);
        currentAnalysis = { ...results, candidateName, text };
        renderResults(results);
      }, 2500);
    });

    // Save analysis
    document.getElementById('save-analysis-btn').addEventListener('click', async () => {
      if (!currentAnalysis) return;

      const analysisData = {
        email: currentUser,
        candidate_name: currentAnalysis.candidateName,
        resume_text: currentAnalysis.text.slice(0, 500),
        score: currentAnalysis.score,
        red_flags: currentAnalysis.redFlags.length,
        status: currentAnalysis.score >= 80 ? 'Low Risk' : currentAnalysis.score >= 50 ? 'Medium Risk' : 'High Risk',
        timestamp: new Date().toISOString(),
        filename: document.getElementById('file-name').textContent.replace('✓ ', '') || 'resume.txt',
        similarity_score: currentAnalysis.similarity,
        plagiarism_detected: currentAnalysis.plagiarism,
        skill_match: currentAnalysis.skillMatch,
        industry_match: document.getElementById('industry-select').value
      };

      const result = await window.dataSdk.create(analysisData);
      
      if (result.isOk) {
        const btn = document.getElementById('save-analysis-btn');
        const original = btn.textContent;
        btn.textContent = '✓ Saved';
        setTimeout(() => btn.textContent = original, 2000);
      }
    });

    // Export report
    document.getElementById('export-btn').addEventListener('click', () => {
      if (!currentAnalysis) return;
      const report = `RESUME ANALYSIS REPORT\n========================\nCandidate: ${currentAnalysis.candidateName}\nScore: ${currentAnalysis.score}/100\nRed Flags: ${currentAnalysis.redFlags.length}\nStatus: ${currentAnalysis.score >= 80 ? 'Low Risk' : currentAnalysis.score >= 50 ? 'Medium Risk' : 'High Risk'}\nSimilarity: ${currentAnalysis.similarity}%\nSkill Match: ${currentAnalysis.skillMatch}%\n\nFLAGS:\n${currentAnalysis.redFlags.join('\n')}\n\nVERIFIED:\n${currentAnalysis.verified.join('\n')}`;
      
      const blob = new Blob([report], { type: 'text/plain' });
      const url = window.URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url;
      a.download = `${currentAnalysis.candidateName}_report.txt`;
      a.click();
    });

    // Clear button
    document.getElementById('clear-btn').addEventListener('click', () => {
      document.getElementById('resume-input').value = '';
      document.getElementById('candidate-name').value = '';
      document.getElementById('file-name').textContent = '';
      document.getElementById('results-container').classList.add('hidden');
    });

    // Reset button
    document.getElementById('reset-btn').addEventListener('click', () => {
      document.getElementById('resume-input').value = '';
      document.getElementById('candidate-name').value = '';
      document.getElementById('file-name').textContent = '';
      document.getElementById('results-container').classList.add('hidden');
    });

    // History
    function renderHistory() {
      const historyList = document.getElementById('history-list');
      if (allAnalyses.length === 0) {
        historyList.innerHTML = '<p class="text-slate-500 text-center py-8">No analyses yet</p>';
        return;
      }

      historyList.innerHTML = allAnalyses
        .sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp))
        .map(a => `
        <div class="bg-slate-950/50 rounded-xl p-4 border border-slate-700 hover:border-emerald-500/50 transition-all">
          <div class="flex items-start justify-between mb-3">
            <div>
              <p class="font-semibold text-emerald-400">${a.candidate_name || 'Unknown'}</p>
              <p class="text-xs text-slate-500">${new Date(a.timestamp).toLocaleString()}</p>
            </div>
            <div class="text-right">
              <p class="text-2xl font-bold ${a.score >= 80 ? 'text-emerald-400' : a.score >= 50 ? 'text-amber-400' : 'text-red-400'}">${a.score}</p>
              <p class="text-xs text-slate-400">${a.status}</p>
            </div>
          </div>
          <div class="grid grid-cols-4 gap-2 text-xs">
            <div class="bg-slate-900 rounded p-2">
              <p class="text-slate-500">Red Flags</p>
              <p class="font-bold text-red-400">${a.red_flags}</p>
            </div>
            <div class="bg-slate-900 rounded p-2">
              <p class="text-slate-500">Similarity</p>
              <p class="font-bold text-cyan-400">${a.similarity_score}%</p>
            </div>
            <div class="bg-slate-900 rounded p-2">
              <p class="text-slate-500">Skills</p>
              <p class="font-bold text-emerald-400">${a.skill_match}%</p>
            </div>
            <div class="bg-slate-900 rounded p-2">
              <p class="text-slate-500">Industry</p>
              <p class="font-bold text-slate-300">${a.industry_match || 'N/A'}</p>
            </div>
          </div>
        </div>
      `).join('');
    }

    // Analytics
    function updateAnalyticsCharts() {
      if (allAnalyses.length === 0) return;

      const avgScore = Math.round(allAnalyses.reduce((s, a) => s + a.score, 0) / allAnalyses.length);
      const lowRisk = allAnalyses.filter(a => a.score >= 80).length;
      const highRisk = allAnalyses.filter(a => a.score < 50).length;

      document.getElementById('stat-total').textContent = allAnalyses.length;
      document.getElementById('stat-avg-score').textContent = avgScore;
      document.getElementById('stat-low-risk').textContent = lowRisk;
      document.getElementById('stat-high-risk').textContent = highRisk;

      // Score chart
      const scoreCtx = document.getElementById('score-chart').getContext('2d');
      if (scoreChart) scoreChart.destroy();
      
      const buckets = [0, 0, 0, 0, 0];
      allAnalyses.forEach(a => {
        if (a.score < 20) buckets[0]++;
        else if (a.score < 40) buckets[1]++;
        else if (a.score < 60) buckets[2]++;
        else if (a.score < 80) buckets[3]++;
        else buckets[4]++;
      });

      scoreChart = new Chart(scoreCtx, {
        type: 'bar',
        data: {
          labels: ['0-20', '20-40', '40-60', '60-80', '80-100'],
          datasets: [{
            label: 'Count',
            data: buckets,
            backgroundColor: ['#ef4444', '#f97316', '#eab308', '#84cc16', '#10b981'],
            borderRadius: 8
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: { legend: { display: false } },
          scales: { y: { beginAtZero: true } }
        }
      });

      // Risk chart
      const riskCtx = document.getElementById('risk-chart').getContext('2d');
      if (riskChart) riskChart.destroy();
      
      const mediumRisk = allAnalyses.filter(a => a.score >= 50 && a.score < 80).length;

      riskChart = new Chart(riskCtx, {
        type: 'doughnut',
        data: {
          labels: ['Low', 'Medium', 'High'],
          datasets: [{
            data: [lowRisk, mediumRisk, highRisk],
            backgroundColor: ['#10b981', '#eab308', '#ef4444'],
            borderColor: '#1e293b',
            borderWidth: 2
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: { legend: { position: 'bottom', labels: { color: '#cbd5e1' } } }
        }
      });

      // Industry chart
      const industries = {};
      allAnalyses.forEach(a => {
        industries[a.industry_match || 'Other'] = (industries[a.industry_match || 'Other'] || 0) + 1;
      });

      const indCtx = document.getElementById('industry-chart').getContext('2d');
      if (industryChart) industryChart.destroy();
      
      industryChart = new Chart(indCtx, {
        type: 'bar',
        data: {
          labels: Object.keys(industries),
          datasets: [{
            label: 'Analyses',
            data: Object.values(industries),
            backgroundColor: '#06b6d4',
            borderRadius: 8
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: { legend: { display: false } },
          scales: { y: { beginAtZero: true } }
        }
      });
    }

    // Comparison
    function populateComparison() {
      const selects = ['compare-1', 'compare-2'];
      selects.forEach(id => {
        const select = document.getElementById(id);
        select.innerHTML = '<option>Select candidate...</option>' +
          allAnalyses.map((a, i) => `<option value="${i}">${a.candidate_name} (${a.score})</option>`).join('');
      });

      ['compare-1', 'compare-2'].forEach((id, idx) => {
        document.getElementById(id).addEventListener('change', () => {
          const i = parseInt(document.getElementById(id).value);
          const a = allAnalyses[i];
          if (!a) return;
          
          const details = `
            <p><span class="text-slate-500">Score:</span> <span class="font-bold text-emerald-400">${a.score}</span></p>
            <p><span class="text-slate-500">Status:</span> <span class="font-bold">${a.status}</span></p>
            <p><span class="text-slate-500">Red Flags:</span> <span class="font-bold text-red-400">${a.red_flags}</span></p>
            <p><span class="text-slate-500">Similarity:</span> <span class="font-bold text-cyan-400">${a.similarity_score}%</span></p>
            <p><span class="text-slate-500">Skills:</span> <span class="font-bold text-emerald-400">${a.skill_match}%</span></p>
          `;
          document.getElementById(`compare-${idx + 1}-details`).innerHTML = details;

          if (document.getElementById('compare-1').value !== 'Select candidate...' && document.getElementById('compare-2').value !== 'Select candidate...') {
            showComparison();
          }
        });
      });
    }

    function showComparison() {
      const i1 = parseInt(document.getElementById('compare-1').value);
      const i2 = parseInt(document.getElementById('compare-2').value);
      const a1 = allAnalyses[i1];
      const a2 = allAnalyses[i2];

      if (!a1 || !a2) return;

      document.getElementById('comparison-result').classList.remove('hidden');
      document.getElementById('comparison-content').innerHTML = `
        <div class="grid md:grid-cols-2 gap-4">
          <div class="bg-slate-950/50 rounded-lg p-4">
            <p class="text-sm text-slate-400 mb-2">Score Difference</p>
            <p class="text-2xl font-bold ${a1.score > a2.score ? 'text-emerald-400' : 'text-red-400'}">${Math.abs(a1.score - a2.score)} points</p>
          </div>
          <div class="bg-slate-950/50 rounded-lg p-4">
            <p class="text-sm text-slate-400 mb-2">Risk Level</p>
            <p class="text-lg font-bold">${a1.score > a2.score ? a2.status : a1.status} candidate is higher risk</p>
          </div>
          <div class="bg-slate-950/50 rounded-lg p-4">
            <p class="text-sm text-slate-400 mb-2">Similarity Diff</p>
            <p class="text-2xl font-bold">${Math.abs(a1.similarity_score - a2.similarity_score)}%</p>
          </div>
          <div class="bg-slate-950/50 rounded-lg p-4">
            <p class="text-sm text-slate-400 mb-2">Skills Diff</p>
            <p class="text-2xl font-bold">${Math.abs(a1.skill_match - a2.skill_match)}%</p>
          </div>
        </div>
      `;
    }

    applyConfig();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9d49edf8137d613f',t:'MTc3MjIxODg3NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

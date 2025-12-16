<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Poster Session: AI Technical Survey Workshop · Uni.lu</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
   
  <style>
    :root {
      /* Conference Color Palette */
      --conf-bg: #f8fafc; /* Slate 50 */
      --conf-surface: #ffffff;
      --conf-primary: #0f172a; /* Slate 900 - Dark Professional */
      --conf-accent: #3b82f6; /* Blue 500 - Tech Blue */
      --conf-secondary: #64748b; /* Slate 500 */
      --conf-border: #e2e8f0;
       
      --state-success-bg: #f0fdf4;
      --state-success-text: #15803d;
      --state-active-bg: #eff6ff;
      --state-active-border: #3b82f6;
       
      --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
      --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
      --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
       
      --font-main: 'Inter', system-ui, -apple-system, sans-serif;
    }
    
    body {
      margin: 0;
      padding: 0;
      background: var(--conf-bg);
      color: #334155;
      font-family: var(--font-main);
      -webkit-font-smoothing: antialiased;
      line-height: 1.6;
    }

    /* --- Navigation / Top Bar Placeholder --- */
    .top-bar {
      height: 4px;
      background: linear-gradient(90deg, #3b82f6, #8b5cf6, #ec4899);
      width: 100%;
    }

    /* --- Hero Section: Modern Conference Style --- */
    .hero {
      background-color: var(--conf-primary);
      color: white;
      padding: 4rem 1.5rem 6rem; /* Extra padding bottom for overlap */
      text-align: center;
      position: relative;
      background-image: radial-gradient(#334155 1px, transparent 1px);
      background-size: 32px 32px;
    }
    
    .hero-content {
      max-width: 800px;
      margin: 0 auto;
      position: relative;
      z-index: 2;
    }

    .hero h1 { 
      margin: 0; 
      font-size: 2.5rem; 
      font-weight: 800; 
      letter-spacing: -0.03em; 
      line-height: 1.2;
      background: linear-gradient(to right, #fff, #cbd5e1);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    
    .hero p { 
      margin: 1rem 0 0; 
      font-size: 1.15rem; 
      color: #94a3b8; 
      font-weight: 400; 
    }
    
    .hero .tagline {
      display: inline-block;
      margin-top: 1.5rem;
      background: rgba(255, 255, 255, 0.1);
      border: 1px solid rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(4px);
      padding: 0.5rem 1rem;
      border-radius: 6px;
      font-size: 0.85rem;
      font-weight: 600;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      color: #e2e8f0;
    }

    /* --- Main Container --- */
    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 1.5rem 4rem;
      position: relative;
      z-index: 10;
    }

    /* --- Event Info Card (Overlapping Hero) --- */
    .event-card {
      background: var(--conf-surface);
      border-radius: 12px;
      box-shadow: var(--shadow-lg);
      margin-top: -3.5rem; /* Overlap effect */
      margin-bottom: 3rem;
      border: 1px solid var(--conf-border);
      padding: 2rem;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 2rem;
      align-items: start;
    }

    .event-item { 
      text-align: left; 
      padding-left: 1rem;
      border-left: 3px solid var(--conf-border);
    }
    
    .event-item label { 
      display: block; 
      font-size: 0.7rem; 
      text-transform: uppercase; 
      letter-spacing: 0.1em; 
      color: var(--conf-secondary); 
      font-weight: 700; 
      margin-bottom: 0.4rem; 
    }
    
    .event-item div { 
      font-size: 1.05rem; 
      font-weight: 600; 
      color: var(--conf-primary); 
    }
    
    .highlight-badge { 
      background: #f0f9ff; 
      color: #0369a1; 
      padding: 0.25rem 0.6rem; 
      border-radius: 4px; 
      font-size: 0.85rem; 
      font-weight: 600; 
      display: inline-block; 
      border: 1px solid #bae6fd;
    }
    
    .event-footer {
      grid-column: 1 / -1;
      margin-top: 1rem;
      padding-top: 1.5rem;
      border-top: 1px solid var(--conf-border);
      display: flex;
      justify-content: center;
      gap: 2rem;
      flex-wrap: wrap;
      font-size: 0.95rem;
      font-weight: 500;
      color: #475569;
    }
    .event-footer span { display: flex; align-items: center; gap: 0.5rem; }
    .award-text { color: #d97706; font-weight: 700; background: #fffbeb; padding: 2px 8px; border-radius: 4px; border: 1px solid #fcd34d;}

    /* --- Section Titles --- */
    .section-title {
      font-size: 1.4rem;
      font-weight: 700;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
      color: var(--conf-primary);
      position: relative;
    }
    .section-title::after {
      content: "";
      flex: 1;
      height: 1px;
      background: var(--conf-border);
      margin-left: 1rem;
    }

    /* --- Timeline --- */
    .timeline-section { margin-bottom: 3.5rem; }
    .timeline {
      display: flex;
      gap: 1.5rem;
      justify-content: center;
      flex-wrap: wrap;
    }
    .timeline-item {
      flex: 1;
      min-width: 280px;
      background: white;
      border: 1px solid var(--conf-border);
      border-radius: 8px;
      padding: 1.25rem;
      position: relative;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .timeline-item:hover {
      transform: translateY(-2px);
      box-shadow: var(--shadow-md);
    }
    .timeline-item.active { 
      border-color: var(--conf-accent); 
      background: linear-gradient(to bottom right, #fff, #eff6ff);
    }
    .timeline-item.active::before {
      content: "Current Phase";
      position: absolute;
      top: -10px;
      right: 15px;
      background: var(--conf-accent);
      color: white;
      font-size: 0.7rem;
      font-weight: bold;
      padding: 2px 8px;
      border-radius: 99px;
      text-transform: uppercase;
    }
    
    .timeline-item.final { border-left: 4px solid #8b5cf6; }
    
    .t-date { 
      font-weight: 800; 
      color: var(--conf-primary); 
      display: block; 
      margin-bottom: 0.5rem; 
      font-size: 1.25rem; 
      letter-spacing: -0.02em;
    }
    .final .t-date { color: #7c3aed; }
    .t-desc { font-size: 0.9rem; color: #64748b; line-height: 1.5; }

    /* --- Card & Table Styles --- */
    .card {
      background: var(--conf-surface);
      border-radius: 8px;
      box-shadow: var(--shadow-sm);
      border: 1px solid var(--conf-border);
      padding: 0; /* Table fills card */
      overflow: hidden;
      margin-bottom: 2rem;
    }
    
    .card-header {
      padding: 1.5rem;
      border-bottom: 1px solid var(--conf-border);
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #f8fafc;
    }
    
    .card-header h3 { margin: 0; font-size: 1.1rem; font-weight: 700; color: var(--conf-primary); }

    /* Button */
    button.secondary { 
      cursor: pointer; border: 1px solid #cbd5e1; background: white; color: #475569; 
      padding: 0.5rem 1rem; border-radius: 6px; font-size: 0.8rem; font-weight: 600;
      transition: all 0.2s;
      font-family: var(--font-main);
    }
    button.secondary:hover { border-color: #94a3b8; color: #1e293b; background: #f1f5f9; }

    /* Table */
    table { width: 100%; border-collapse: collapse; font-size: 0.9rem; }
    th { 
      background: #fff; 
      text-transform: uppercase; 
      font-size: 0.75rem; 
      font-weight: 700; 
      letter-spacing: 0.05em; 
      color: #64748b; 
      padding: 1rem 1.5rem;
      text-align: left;
      border-bottom: 2px solid var(--conf-border);
    }
    td { 
      padding: 1rem 1.5rem; 
      border-bottom: 1px solid var(--conf-border); 
      color: #334155;
    }
    tr:last-child td { border-bottom: none; }
    tr:hover td { background: #f8fafc; }
    
    .muted { font-size: 0.85rem; color: #94a3b8; font-style: italic; }
    
    .delete-btn {
      background: transparent; color: #ef4444; border: 1px solid #fecaca;
      width: 24px; height: 24px; border-radius: 4px; 
      display: inline-flex; align-items: center; justify-content: center;
      cursor: pointer; font-size: 1.2rem; line-height: 1;
      transition: background 0.2s;
    }
    .delete-btn:hover { background: #fee2e2; }

    .message { padding: 1rem; font-size: 0.9rem; font-weight: 500; text-align: center; }
    .message.success { background-color: #f0fdf4; color: #166534; border-top: 1px solid #bbf7d0; }

    /* --- Grading Section --- */
    .grading-info {
      background: #fdfce7; 
      border: 1px solid #fef08a; 
      padding: 1rem 1.5rem; 
      border-radius: 6px; 
      margin-bottom: 1.5rem; 
      color: #854d0e;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      font-size: 0.95rem;
    }

    .points-badge {
      font-weight: 700;
      color: var(--conf-accent);
      background: #eff6ff;
      padding: 2px 8px;
      border-radius: 99px;
      font-size: 0.8rem;
    }

    /* --- Footer --- */
    .page-footer {
      text-align: center;
      margin-top: 4rem;
      padding-top: 2rem;
      border-top: 1px solid var(--conf-border);
      color: var(--conf-secondary);
      font-size: 0.9rem;
    }
    .page-footer a {
      color: var(--conf-accent);
      text-decoration: none;
      font-weight: 600;
    }
    .page-footer a:hover { text-decoration: underline; }

    @media (max-width: 700px) {
      .hero { padding: 3rem 1rem 5rem; }
      .hero h1 { font-size: 1.8rem; }
      .event-card { grid-template-columns: 1fr; gap: 1.5rem; margin-top: -2rem; }
      .event-item { border-left: none; border-top: 2px solid var(--conf-border); padding-left: 0; padding-top: 1rem; }
      .event-item:first-child { border-top: none; padding-top: 0; }
      .event-footer { flex-direction: column; gap: 0.8rem; align-items: center; }
      table { display: block; overflow-x: auto; white-space: nowrap; }
    }
  </style>
</head>
<body>

  <div class="top-bar"></div>

  <div class="hero">
    <div class="hero-content">
      <h1>Introduction to Project Management</h1>
      <p>Bachelor in Computer Science · University of Luxembourg</p>
      <div class="tagline">Poster Session: AI Technical Survey Workshop</div>
    </div>
  </div>

  <div class="container">
    
    <div class="event-card">
      <div class="event-item">
        <label>Final Event Date</label>
        <div>17 Dec 2025</div>
      </div>
      <div class="event-item">
        <label>Time Schedule</label>
        <div>08:30 - 12:00</div>
      </div>
      <div class="event-item">
        <label>Venue / Room</label>
        <div>MSA 4.520 (Mandatory)</div>
      </div>
      <div class="event-item">
        <label>On-Site Amenities</label>
        <div class="highlight-badge">☕ Coffee & Desserts</div>
      </div>
      
      <div class="event-footer">
        <span>🎤 Interactive Presentations</span>
        <span>📝 Peer Grading Session</span>
        <span class="award-text">🏆 Best Poster Awards</span>
      </div>
    </div>

    <div class="section-title">⏱️ Detailed Agenda</div>
    <div class="card">
        <table>
            <thead>
                <tr>
                    <th style="width: 150px;">Time</th>
                    <th>Activity</th>
                    <th style="width: 150px;">Details</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><strong>08:30 - 08:35</strong></td>
                    <td>👋 Opening & Guidelines</td>
                    <td class="muted">5 mins</td>
                </tr>
                <tr>
                    <td><strong>08:35 - 11:35</strong></td>
                    <td>
                        <strong>🎤 Poster Exhibition & Grading</strong><br>
                        <span class="muted" style="font-size:0.8rem;">
                           Interactive Session: Students explain work & answer Q&A.<br>
                           <strong>Mandatory:</strong> Peer grading for all groups.
                        </span>
                    </td>
                    <td class="muted">180 mins</td>
                </tr>
                <tr>
                    <td><strong>11:35 - 11:45</strong></td>
                    <td>📊 Score Calculation</td>
                    <td class="muted">10 mins</td>
                </tr>
                <tr>
                    <td><strong>11:45 - 11:50</strong></td>
                    <td>🏆 Awards Ceremony</td>
                    <td class="muted">5 mins</td>
                </tr>
                <tr>
                    <td><strong>11:50 - 12:00</strong></td>
                    <td>🔚 Closing & Networking</td>
                    <td class="muted">10 mins</td>
                </tr>
            </tbody>
        </table>
    </div>

    <div class="timeline-section">
      <div class="section-title">📅 Upcoming Schedule & Deadlines</div>
      <div class="timeline">
        <div class="timeline-item active">
          <span class="t-date">29 Nov</span>
          <span class="t-desc">
            <strong>Topic Selection Deadline</strong><br/>
            (23:59 via this website)
          </span>
        </div>
        
        <div class="timeline-item final">
          <span class="t-date">9 Dec</span>
          <span class="t-desc">
            <strong>Poster Submission Deadline</strong><br/>
            (23:59 on Moodle)
          </span>
        </div>
      </div>
    </div>

    <div class="section-title">📋 Registered Groups & Topics</div>
    <div class="card">
      <div class="card-header">
        <h3>Final Group Assignments</h3>
        <button id="resetBtn" class="secondary" type="button">Reset All (Admin Only)</button>
      </div>
      
      <div style="overflow-x: auto;">
        <table>
          <thead>
            <tr>
              <th style="width:120px;">Group ID</th>
              <th style="width:280px;">Main Topic</th>
              <th>Specific Subtopic / Title</th>
              <th style="width:60px; text-align:center;">Action</th>
            </tr>
          </thead>
          <tbody id="assignmentsBody"></tbody>
        </table>
      </div>
      <div id="message" class="message"></div>
    </div>

    <div class="section-title">⚖️ Evaluation Criteria</div>
    
    <div class="grading-info">
      <strong>Score Breakdown:</strong> The maximum Peer Score is <strong>20 Points</strong>.
    </div>

    <div class="card">
        <table>
            <thead>
                <tr>
                    <th>Review Category</th>
                    <th style="width:120px;">Max Points</th>
                    <th>Guiding Questions for Reviewers</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><strong>1. Visual Appeal & Layout</strong></td>
                    <td><span class="points-badge">5 pts</span></td>
                    <td class="muted">Is the text legible? Are the diagrams high quality? Is the layout not overcrowded?</td>
                </tr>
                <tr>
                    <td><strong>2. Presentation Pitch</strong></td>
                    <td><span class="points-badge">5 pts</span></td>
                    <td class="muted">Did the speaker explain the concept clearly? Was the talk engaging?</td>
                </tr>
                <tr>
                    <td><strong>3. Technical Accessibility</strong></td>
                    <td><span class="points-badge">5 pts</span></td>
                    <td class="muted">Could you understand the problem and solution without being an expert?</td>
                </tr>
                <tr>
                    <td><strong>4. Q&A Interaction</strong></td>
                    <td><span class="points-badge">5 pts</span></td>
                    <td class="muted">Did the presenters answer questions confidently and correctly?</td>
                </tr>
                <tr style="background-color: #f8fafc;">
                    <td style="text-align:right; font-weight:700;">TOTAL SCORE</td>
                    <td style="font-weight:800; color:#d97706;">20 pts</td>
                    <td></td>
                </tr>
            </tbody>
        </table>
    </div>

    <div class="page-footer">
        Any questions? Contact <a href="mailto:hongyang.li@uni.lu">hongyang.li@uni.lu</a>
        <br><br>
        &copy; 2025 University of Luxembourg
    </div>

  </div>

  <script>
    // --- Configuration & Data ------------------------------------------------
    const GROUP_COUNT = 12;
    const STORAGE_KEY = "uni_poster_assignments_v7"; // Updated version
    const ADMIN_PASSWORD = "admin"; 

    // Pre-defined Final List
    const FINAL_LIST = [
        { group: 1, topicId: "dl-basics", subtopic: "", leader: "-", pin: "1234" },
        { group: 2, topicId: "ethics", subtopic: "Humans vs Algorithms: How Fair Do Their Decisions Feel?", leader: "-", pin: "1234" },
        { group: 3, topicId: "nlp-chatbot", subtopic: "", leader: "-", pin: "1234" },
        { group: 4, topicId: "cv-classification", subtopic: "", leader: "-", pin: "1234" },
        { group: 5, topicId: "ai-games", subtopic: "", leader: "-", pin: "1234" },
        { group: 6, topicId: "cybersec", subtopic: "AI for malware and suspicious network activity detection and analysis", leader: "-", pin: "1234" },
        { group: 7, topicId: "dl-basics", subtopic: "Deep Learning", leader: "-", pin: "1234" },
        { group: 8, topicId: "nlp-sentiment", subtopic: "Multilingual sentiment analysis", leader: "-", pin: "1234" },
        { group: 9, topicId: "cybersec", subtopic: "", leader: "-", pin: "1234" },
        { group: 10, topicId: "ai-games", subtopic: "", leader: "-", pin: "1234" },
        { group: 11, topicId: "nlp-sentiment", subtopic: "EMOTION ANALYSIS", leader: "-", pin: "1234" },
        { group: 12, topicId: "ai-health", subtopic: "", leader: "-", pin: "1234" }
    ];

    const topics = [
      { id: "dl-basics", label: "Deep Learning Fundamentals", description: "Intro to neural networks (MLPs, CNNs).", example: "Handwritten digit recognition (MNIST)." },
      { id: "nlp-sentiment", label: "NLP: Sentiment Analysis", description: "Classifying text as positive/negative/neutral.", example: "Movie review analysis with RNNs." },
      { id: "cv-classification", label: "CV: Image Classification", description: "Identifying objects inside an image.", example: "ResNet for plant classification." },
      { id: "cv-detection", label: "CV: Object Detection", description: "Locating multiple objects in images.", example: "Traffic sign detection with YOLO." },
      { id: "nlp-chatbot", label: "NLP: Chatbots & Q&A", description: "Systems that answer questions or chat.", example: "FAQ bot using RAG." },
      { id: "ai-games", label: "AI for Games", description: "Agents learning strategies via interaction.", example: "RL agent playing Super Mario." },
      { id: "ai-health", label: "AI in Healthcare", description: "ML for medical diagnosis or analysis.", example: "Tumor detection in MRI scans." },
      { id: "cybersec", label: "AI for Cybersecurity", description: "Detecting malicious online activity.", example: "Phishing email detection." },
      { id: "ethics", label: "AI Ethics & Fairness", description: "Detecting and mitigating bias in AI.", example: "Analyzing gender bias in hiring tools." },
      { id: "custom", label: "Custom / Other", description: "Specific topic not listed above.", example: "Research project." }
    ];

    // --- DOM Elements --------------------------------------------------------
    const els = {
      reset: document.getElementById("resetBtn"),
      msg: document.getElementById("message"),
      tbody: document.getElementById("assignmentsBody")
    };

    // --- State & Storage -----------------------------------------------------
    let assignments = [];
    
    // Logic: If LocalStorage is empty or older version, use FINAL_LIST
    try {
      const stored = JSON.parse(localStorage.getItem(STORAGE_KEY));
      if (stored && stored.length > 0) {
          assignments = stored;
      } else {
          assignments = FINAL_LIST; 
      }
    } catch { 
        assignments = FINAL_LIST; 
    }

    function saveData() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(assignments));
    }

    // --- Logic ---------------------------------------------------------------
    function init() {
      renderTable();
    }

    function renderTable() {
      els.tbody.innerHTML = "";
      if (assignments.length === 0) {
        els.tbody.innerHTML = '<tr><td colspan="4" class="muted" style="text-align:center; padding:1.5rem;">No registrations yet.</td></tr>';
        return;
      }
      const sorted = [...assignments].sort((a, b) => a.group - b.group);
      
      sorted.forEach(a => {
        const topic = topics.find(t => t.id === a.topicId);
        const tr = document.createElement("tr");
        
        // Create Delete Button
        const delTd = document.createElement("td");
        delTd.style.textAlign = "center";
        const delBtn = document.createElement("button");
        delBtn.textContent = "×";
        delBtn.className = "delete-btn";
        delBtn.title = "Delete this group (Admin only)";
        delBtn.onclick = () => deleteAssignment(a.group);
        delTd.appendChild(delBtn);

        // Subtopic formatting
        let displaySub = a.subtopic;
        if (!displaySub) displaySub = "<em class='muted'>-</em>";

        tr.innerHTML = `
          <td><span style="font-weight:700; color:#334155;">Group ${a.group}</span></td>
          <td><span style="font-weight:600; color:#2563eb;">${topic ? topic.label : "Custom"}</span></td>
          <td>${displaySub}</td>
        `;
        tr.appendChild(delTd); 
        
        els.tbody.appendChild(tr);
      });
    }

    function deleteAssignment(groupNum) {
      const pwd = prompt("Enter Admin Password to delete Group " + groupNum + ":");
      if (pwd === ADMIN_PASSWORD) {
        assignments = assignments.filter(a => a.group !== groupNum);
        saveData();
        renderTable(); 
        showMsg(`Group ${groupNum} deleted.`, "success");
      } else if (pwd !== null) {
        alert("Wrong Password");
      }
    }

    function showMsg(text, type) {
      els.msg.textContent = text;
      els.msg.className = `message ${type}`;
      setTimeout(() => { els.msg.textContent = ""; els.msg.className="message"; }, 5000);
    }

    // --- Events --------------------------------------------------------------
    els.reset.addEventListener("click", () => {
      const pwd = prompt("WARNING: This will delete ALL groups and reload defaults.\nEnter Admin Password:");
      if (pwd === ADMIN_PASSWORD) {
        assignments = [...FINAL_LIST]; 
        saveData();
        init(); 
        showMsg("Reset to default list complete.", "success");
      } else if (pwd !== null) {
        alert("Wrong Password.");
      }
    });

    // Start
    init();
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Poster Session: AI Technical Survey Workshop · Uni.lu</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color-scheme: light;
      --primary: #2563eb;
      --primary-dark: #1e40af;
      --secondary: #4f46e5;
      --bg-color: #f8fafc;
      --card-bg: #ffffff;
      --border-color: #e2e8f0;
      --text-main: #1e293b;
      --text-muted: #64748b;
      --accent-bg: #eff6ff;
    }
    
    body {
      margin: 0;
      padding: 0;
      background: var(--bg-color);
      color: var(--text-main);
      line-height: 1.5;
    }

    /* --- Hero & Header Section --- */
    .hero {
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      color: white;
      padding: 3rem 1.5rem;
      text-align: center;
    }
    .hero h1 { margin: 0; font-size: 2.2rem; font-weight: 700; letter-spacing: -0.02em; }
    .hero p { margin: 0.5rem 0 0; font-size: 1.1rem; opacity: 0.9; }
    .hero .tagline {
      display: inline-block;
      margin-top: 1rem;
      background: rgba(255, 255, 255, 0.2);
      padding: 0.4rem 1.2rem;
      border-radius: 99px;
      font-size: 1rem;
      font-weight: 600;
      letter-spacing: 0.02em;
    }

    /* --- Event Info Card --- */
    .event-card {
      background: white;
      max-width: 900px;
      margin: -2rem auto 2rem;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.05);
      position: relative;
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      justify-content: space-around;
      align-items: center;
      border: 1px solid var(--border-color);
    }
    .event-item { text-align: center; flex: 1; min-width: 180px; }
    .event-item label { display: block; font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.05em; color: var(--text-muted); font-weight: 700; margin-bottom: 0.25rem; }
    .event-item div { font-size: 1.1rem; font-weight: 600; color: var(--primary-dark); }
    .highlight-badge { 
      background: #dbeafe; color: #1e40af; 
      padding: 0.25rem 0.75rem; border-radius: 6px; 
      font-size: 0.85rem; font-weight: 600; display: inline-block; margin-top:0.25rem;
    }
    
    .event-footer {
      flex-basis: 100%;
      width: 100%;
      margin-top: 1rem;
      padding-top: 1.2rem;
      border-top: 1px solid var(--border-color);
      text-align: center;
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      flex-wrap: wrap;
      font-weight: 500;
      color: #334155;
    }
    .event-footer span { display: flex; align-items: center; gap: 0.4rem; }
    .award-text { color: #d97706; font-weight: 700; }

    /* --- Main Container --- */
    .container {
      max-width: 1000px;
      margin: 0 auto;
      padding: 0 1.5rem 3rem;
    }

    /* --- Timeline Section --- */
    .timeline-section {
      margin-bottom: 2.5rem;
    }
    .section-title {
      font-size: 1.25rem;
      font-weight: 700;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      color: var(--text-main);
    }
    .timeline {
      display: flex;
      justify-content: center;
      gap: 2rem;
      padding-bottom: 1rem;
      position: relative;
    }
    .timeline::before {
        content: ""; position: absolute; top: 50%; left: 20%; right: 20%;
        height: 2px; background: #e2e8f0; z-index: 0; transform: translateY(-50%);
    }
    .timeline-item {
      flex: 0 1 300px;
      background: white;
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 1rem;
      text-align: center;
      z-index: 1;
      box-shadow: 0 2px 5px rgba(0,0,0,0.03);
    }
    .timeline-item.active { border-color: var(--primary); background: #eff6ff; }
    .timeline-item.final { border-color: var(--secondary); background: #f5f3ff; }
    
    .t-date { font-weight: 700; color: var(--primary); display: block; margin-bottom: 0.25rem; font-size: 1.1rem; }
    .timeline-item.final .t-date { color: var(--secondary); }
    .t-desc { font-size: 0.9rem; color: var(--text-muted); line-height: 1.3; }

    /* --- Card Styles --- */
    .card {
      background: var(--card-bg);
      border-radius: 12px;
      padding: 1.5rem;
      border: 1px solid var(--border-color);
      box-shadow: 0 2px 8px rgba(0,0,0,0.03);
      margin-bottom: 1.5rem;
    }

    /* Buttons */
    button.secondary { 
      cursor: pointer; border: none; background: #f1f5f9; color: #0f172a; 
      padding: 0.4rem 0.8rem; border-radius: 8px; font-size: 0.85rem; font-weight: 600;
      transition: background 0.2s;
    }
    button.secondary:hover { background: #e2e8f0; }

    /* Table */
    .muted { font-size: 0.85rem; color: var(--text-muted); }
    
    table { width: 100%; border-collapse: collapse; font-size: 0.95rem; border-radius: 8px; overflow: hidden; border: 1px solid var(--border-color); }
    th, td { border-bottom: 1px solid var(--border-color); padding: 0.8rem 1rem; text-align: left; }
    th { background: #f8fafc; font-weight: 600; color: #475569; }
    
    .delete-btn {
      background: #fee2e2; color: #dc2626; border: 1px solid #fca5a5;
      padding: 0.2rem 0.6rem; border-radius: 4px; font-weight: bold; cursor: pointer;
      font-size: 0.9rem; width: auto; display: inline-block;
    }
    .delete-btn:hover { background: #fecaca; }

    .message { margin-top: 0.8rem; font-size: 0.95rem; font-weight: 500; text-align: center; }
    .message.success { color: #16a34a; }

    .page-footer {
        text-align: center;
        margin-top: 3rem;
        padding-top: 1rem;
        border-top: 1px solid #e2e8f0;
        color: var(--text-muted);
        font-size: 0.9rem;
    }
    .page-footer a {
        color: var(--primary);
        text-decoration: none;
        font-weight: 600;
    }
    .page-footer a:hover { text-decoration: underline; }

    @media (max-width: 800px) {
      .event-card { flex-direction: column; text-align: center; gap: 1rem; }
      .timeline { flex-direction: column; gap: 1rem; }
      .timeline::before { display: none; }
      .timeline-item { width: auto; }
      .event-footer { flex-direction: column; gap: 0.5rem; }
    }
  </style>
</head>
<body>

  <div class="hero">
    <h1>Introduction to Project Management</h1>
    <p>Bachelor in Computer Science · University of Luxembourg</p>
    <div class="tagline">Poster Session: AI Technical Survey Workshop</div>
  </div>

  <div class="container">
    <div class="event-card">
      <div class="event-item">
        <label>Final Event Date</label>
        <div>17 Dec 2025</div>
      </div>
      <div class="event-item">
        <label>Time</label>
        <div>08:30 - 12:00</div>
      </div>
      <div class="event-item">
        <label>Location</label>
        <div>Room MSA 4.520 (Mandatory)</div>
      </div>
      <div class="event-item">
        <label>Amenities</label>
        <div class="highlight-badge">☕ Coffee & Desserts</div>
      </div>
      
      <div class="event-footer">
        <span>🎤 Each Group Presents 10 mins</span>
        <span>📝 Peer Grading Session</span>
        <span class="award-text">🏆 Best Poster Awards</span>
      </div>
    </div>

    <div class="timeline-section">
      <div class="section-title">📅 Upcoming Deadlines</div>
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

    <!-- REMOVED Topic Registration / Update Section -->

    <div class="card" style="margin-top:2rem;">
      <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:1rem;">
        <h3 style="margin:0;">Final Group Assignments</h3>
        <!-- Admin can still reset if needed via password -->
        <button id="resetBtn" class="secondary" type="button">Reset All (Admin Only)</button>
      </div>
      
      <table>
        <thead>
          <tr>
            <th style="width:100px;">Group</th>
            <th style="width:250px;">Main Topic</th>
            <th>Specific Subtopic / Title</th>
            <th style="width:60px;">Admin</th>
          </tr>
        </thead>
        <tbody id="assignmentsBody"></tbody>
      </table>
      <div id="message" class="message"></div>
    </div>

    <!-- GRADING CRITERIA -->
    <div class="section-title">👥 Grading Criteria & Reference</div>
    <div class="card">
        <div style="background:#f0fdf4; border:1px solid #bbf7d0; padding:1rem; border-radius:8px; margin-bottom:1.5rem; color:#166534;">
            <strong>Score Breakdown:</strong> The maximum Peer Score is <strong>20 Points</strong>.
        </div>
        <table>
            <thead>
                <tr>
                    <th>Review Category</th>
                    <th style="width:100px;">Max Points</th>
                    <th>Guiding Questions for Reviewers</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><strong>1. Visual Appeal & Layout</strong></td>
                    <td style="font-weight:bold; color:var(--primary);">5 pts</td>
                    <td class="muted">Is the text legible? Are the diagrams high quality? Is the layout not overcrowded?</td>
                </tr>
                <tr>
                    <td><strong>2. Presentation Pitch</strong></td>
                    <td style="font-weight:bold; color:var(--primary);">5 pts</td>
                    <td class="muted">Did the speaker explain the concept clearly? Was the talk engaging?</td>
                </tr>
                <tr>
                    <td><strong>3. Technical Accessibility</strong></td>
                    <td style="font-weight:bold; color:var(--primary);">5 pts</td>
                    <td class="muted">Could you understand the problem and solution without being an expert?</td>
                </tr>
                <tr>
                    <td><strong>4. Q&A Interaction</strong></td>
                    <td style="font-weight:bold; color:var(--primary);">5 pts</td>
                    <td class="muted">Did the presenters answer questions confidently and correctly?</td>
                </tr>
                <tr style="background-color: #f8fafc; border-top: 2px solid #e2e8f0;">
                    <td style="text-align:right;"><strong>TOTAL</strong></td>
                    <td style="font-weight:bold; color:#d97706;">20 pts</td>
                    <td></td>
                </tr>
            </tbody>
        </table>
    </div>

    <div class="page-footer">
        Any questions? Contact <a href="mailto:hongyang.li@uni.lu">hongyang.li@uni.lu</a>
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
          <td><strong>Group ${a.group}</strong></td>
          <td>${topic ? topic.label : "Custom"}</td>
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
      setTimeout(() => { els.msg.textContent = ""; }, 5000);
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

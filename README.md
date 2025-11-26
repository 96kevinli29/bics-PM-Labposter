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
    
    /* New Style for Event Footer (Awards/Format) */
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
      justify-content: center; /* Center the two items */
      gap: 2rem;
      padding-bottom: 1rem;
      position: relative;
    }
    /* Simple connector line */
    .timeline::before {
        content: ""; position: absolute; top: 50%; left: 20%; right: 20%;
        height: 2px; background: #e2e8f0; z-index: 0; transform: translateY(-50%);
    }
    .timeline-item {
      flex: 0 1 300px; /* Fixed width for better look with only 2 items */
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

    /* --- General Card & Form Styles --- */
    .card {
      background: var(--card-bg);
      border-radius: 12px;
      padding: 1.5rem;
      border: 1px solid var(--border-color);
      box-shadow: 0 2px 8px rgba(0,0,0,0.03);
      margin-bottom: 1.5rem;
    }
    .grid {
      display: grid;
      grid-template-columns: 1.3fr 1fr;
      gap: 2rem;
      align-items: flex-start;
    }
    
    /* Form Inputs */
    label { display: block; font-size: 0.9rem; margin-bottom: 0.35rem; font-weight: 600; color: #334155; }
    select, input[type="text"], input[type="password"] {
      width: 100%; padding: 0.6rem; font-size: 0.95rem; border-radius: 8px;
      border: 1px solid #cbd5e1; box-sizing: border-box; transition: all 0.2s;
    }
    select:focus, input:focus { outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1); }
    
    /* Buttons */
    button {
      cursor: pointer; border: none; background: var(--primary); color: white;
      font-weight: 600; padding: 0.75rem 1rem; border-radius: 8px; width: 100%;
      font-size: 0.95rem; transition: background 0.2s;
    }
    button:hover { background: var(--primary-dark); }
    button.secondary { background: #f1f5f9; color: #0f172a; width: auto; padding: 0.4rem 0.8rem; font-size: 0.85rem; }
    button.secondary:hover { background: #e2e8f0; }

    /* Topic Details & Table */
    .muted { font-size: 0.85rem; color: var(--text-muted); }
    .info-box { background: #eff6ff; border: 1px solid #bfdbfe; color: #1e40af; padding: 0.8rem; border-radius: 8px; font-size: 0.9rem; margin-top: 1rem; display: none; }
    .info-box a { color: #1e40af; font-weight: 700; }
    
    table { width: 100%; border-collapse: collapse; font-size: 0.9rem; border-radius: 8px; overflow: hidden; border: 1px solid var(--border-color); }
    th, td { border-bottom: 1px solid var(--border-color); padding: 0.7rem 1rem; text-align: left; }
    th { background: #f8fafc; font-weight: 600; color: #475569; }
    .leader-name { color: var(--primary); font-weight: 500; }
    
    /* Messages */
    .message { margin-top: 0.8rem; font-size: 0.95rem; font-weight: 500; text-align: center; }
    .message.error { color: #dc2626; }
    .message.success { color: #16a34a; }

    @media (max-width: 800px) {
      .grid { grid-template-columns: 1fr; }
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
        <span>🎤 Each Group Presents</span>
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

    <div class="section-title">📝 Poster Topic Registration</div>
    <div class="card">
      <p class="muted" style="margin-top:0;">
        <strong>Instructions:</strong> Select your group number and a topic. You must set a <strong>PIN</strong> to protect your registration. You will need this PIN to modify your choice later.
      </p>

      <div class="grid">
        <div>
          <div style="display: flex; gap: 1rem; margin-bottom: 1rem; flex-wrap: wrap;">
            <div style="flex: 0 0 110px;">
              <label for="groupSelect">Group #</label>
              <select id="groupSelect">
                <option value="">Select...</option>
              </select>
            </div>
            <div style="flex: 1; min-width: 140px;">
              <label for="leaderInput">Group Leader</label>
              <input type="text" id="leaderInput" placeholder="Full Name" />
            </div>
            <div style="flex: 0 0 100px;">
              <label for="pinInput">PIN</label>
              <input type="password" id="pinInput" placeholder="4-digit" maxlength="6" />
            </div>
          </div>

          <div style="margin-bottom: 1rem;">
            <label for="topicSelect">Select Main Topic</label>
            <select id="topicSelect">
              <option value="">Choose a topic area...</option>
            </select>
            
            <div id="customTopicAlert" class="info-box">
              <strong>Proposing a new topic?</strong><br/>
              Please email the Teaching Assistant at 
              <a href="mailto:hongyang.li@uni.lu?subject=Poster Topic Proposal">hongyang.li@uni.lu</a> 
              to verify suitability.<br/><br/>
              <em>If approved, enter your title below.</em>
            </div>
          </div>

          <div style="margin-bottom: 1.5rem;">
            <label for="subtopicInput">Specific Subtopic / Poster Title</label>
            <input type="text" id="subtopicInput" placeholder="e.g. Object Detection with YOLOv8" />
            <div class="muted" style="margin-top:0.3rem;">Required for Custom topics, optional for others.</div>
          </div>

          <button id="confirmBtn">Confirm Registration</button>
          <div id="message" class="message"></div>
        </div>

        <div style="background: #f8fafc; border-radius: 8px; padding: 1.2rem; border:1px solid #e2e8f0;">
          <h3 style="margin-top:0; font-size:1.1rem;">Topic Details</h3>
          <div id="topicDetails" class="muted">
            <p>Select a topic from the dropdown to see description and examples.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="card" style="margin-top:2rem;">
      <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:1rem;">
        <h3 style="margin:0;">Current Group Registrations</h3>
        <button id="resetBtn" class="secondary" type="button">Reset (Admin Only)</button>
      </div>
      
      <table>
        <thead>
          <tr>
            <th style="width:80px;">Group</th>
            <th style="width:180px;">Leader</th>
            <th>Main Topic Area</th>
            <th>Specific Title</th>
          </tr>
        </thead>
        <tbody id="assignmentsBody"></tbody>
      </table>
    </div>
  </div>

  <script>
    // --- Configuration & Data ------------------------------------------------
    const GROUP_COUNT = 12;
    const STORAGE_KEY = "uni_poster_assignments_v5"; 
    const ADMIN_PASSWORD = "admin"; 

    const topics = [
      { id: "dl-basics", label: "Deep Learning Fundamentals", description: "Intro to neural networks (MLPs, CNNs).", example: "Handwritten digit recognition (MNIST)." },
      { id: "nlp-sentiment", label: "NLP: Sentiment Analysis", description: "Classifying text as positive/negative/neutral.", example: "Movie review analysis with RNNs." },
      { id: "cv-classification", label: "CV: Image Classification", description: "Identifying objects inside an image.", example: "ResNet for plant classification." },
      { id: "recommender", label: "Recommender Systems", description: "Suggesting items based on user history.", example: "Movie recommendation via collaborative filtering." },
      { id: "cv-detection", label: "CV: Object Detection", description: "Locating multiple objects in images.", example: "Traffic sign detection with YOLO." },
      { id: "nlp-chatbot", label: "NLP: Chatbots & Q&A", description: "Systems that answer questions or chat.", example: "FAQ bot using RAG." },
      { id: "time-series", label: "Time Series Forecasting", description: "Predicting future values from past sequences.", example: "Stock price prediction with LSTM." },
      { id: "ai-games", label: "AI for Games", description: "Agents learning strategies via interaction.", example: "RL agent playing Super Mario." },
      { id: "ai-health", label: "AI in Healthcare", description: "ML for medical diagnosis or analysis.", example: "Tumor detection in MRI scans." },
      { id: "ai-finance", label: "AI in FinTech", description: "Fraud detection or risk scoring.", example: "Credit card fraud anomaly detection." },
      { id: "cybersec", label: "AI for Cybersecurity", description: "Detecting malicious online activity.", example: "Phishing email detection." },
      { id: "xai", label: "Explainable AI (XAI)", description: "Making models interpretable.", example: "Explaining loan decisions with SHAP." },
      { id: "audio-ai", label: "Audio & Speech Processing", description: "Speech recognition or sound classification.", example: "Music genre classification." },
      { id: "ethics", label: "AI Ethics & Fairness", description: "Detecting and mitigating bias in AI.", example: "Analyzing gender bias in hiring tools." },
      { id: "gen-ai", label: "Generative AI", description: "Creating new content (text/images).", example: "Image generation with Diffusion models." },
      { id: "gnn", label: "Graph Neural Networks", description: "Learning from graph-structured data.", example: "Molecular property prediction." },
      { id: "autonomous", label: "Autonomous Systems", description: "Perception and planning for robots.", example: "Lane keeping simulation." },
      { id: "federated", label: "Federated Learning", description: "Privacy-preserving distributed training.", example: "Training on mobile devices." },
      { id: "multi-modal", label: "Multi-modal Learning", description: "Combining text, image, or audio.", example: "Visual Question Answering (VQA)." },
      { id: "edge-ai", label: "Edge AI / TinyML", description: "AI on low-power devices.", example: "Keyword spotting on Raspberry Pi." },
      { id: "custom", label: "Propose Custom Topic", description: "Your own idea (requires approval).", example: "Research project agreed with TA." }
    ];

    // --- DOM Elements --------------------------------------------------------
    const els = {
      group: document.getElementById("groupSelect"),
      leader: document.getElementById("leaderInput"),
      pin: document.getElementById("pinInput"), 
      topic: document.getElementById("topicSelect"),
      subtopic: document.getElementById("subtopicInput"),
      details: document.getElementById("topicDetails"),
      customAlert: document.getElementById("customTopicAlert"),
      confirm: document.getElementById("confirmBtn"),
      reset: document.getElementById("resetBtn"),
      msg: document.getElementById("message"),
      tbody: document.getElementById("assignmentsBody")
    };

    // --- State & Storage -----------------------------------------------------
    let assignments = [];
    try {
      assignments = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
    } catch { assignments = []; }

    function saveData() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(assignments));
    }

    function getAssignedMap() {
      return new Map(assignments.map(a => [a.topicId, a.group]));
    }

    function getGroupAssignment(groupNum) {
      return assignments.find(a => a.group === groupNum);
    }

    // --- Logic ---------------------------------------------------------------
    function init() {
      // Populate Groups
      els.group.innerHTML = '<option value="">Select...</option>';
      for (let i = 1; i <= GROUP_COUNT; i++) {
        const opt = document.createElement("option");
        opt.value = i;
        opt.textContent = `Group ${i}`;
        els.group.appendChild(opt);
      }
      renderTopicOptions();
      renderTable();
    }

    function renderTopicOptions() {
      const assignedMap = getAssignedMap();
      const currentGroup = Number(els.group.value);
      const myAssignment = currentGroup ? getGroupAssignment(currentGroup) : null;
      const currentTopicSelection = els.topic.value; 

      els.topic.innerHTML = '<option value="">Choose a topic area...</option>';

      topics.forEach(t => {
        const opt = document.createElement("option");
        opt.value = t.id;
        let label = t.label;
        const isTaken = assignedMap.has(t.id);
        const takenByMe = myAssignment && myAssignment.topicId === t.id;

        if (t.id !== 'custom' && isTaken) {
          label += ` (Taken by Group ${assignedMap.get(t.id)})`;
          if (!takenByMe) opt.disabled = true;
        }
        opt.textContent = label;
        els.topic.appendChild(opt);
      });

      // Restore or Clear Form
      if (myAssignment) {
        els.topic.value = myAssignment.topicId;
        els.subtopic.value = myAssignment.subtopic || "";
        els.leader.value = myAssignment.leader || "";
        els.confirm.textContent = "Update Registration";
        els.pin.placeholder = "Enter PIN to edit"; 
        updateDetails(myAssignment.topicId);
      } else {
        if(currentTopicSelection && !assignedMap.has(currentTopicSelection)) {
          els.topic.value = currentTopicSelection;
        } else {
          els.topic.value = "";
        }
        els.leader.value = "";
        els.subtopic.value = "";
        els.pin.value = "";
        els.pin.placeholder = "Set new PIN";
        els.confirm.textContent = "Confirm Registration";
        updateDetails(els.topic.value || "");
      }
    }

    function updateDetails(topicId) {
      const topic = topics.find(t => t.id === topicId);
      els.customAlert.style.display = (topicId === 'custom') ? "block" : "none";

      if (!topic) {
        els.details.innerHTML = '<p class="muted">Select a topic to see details.</p>';
        return;
      }
      
      els.details.innerHTML = `
        <h4 style="margin-bottom:0.5rem; color:#1e3a8a;">${topic.label}</h4>
        <p style="margin-bottom:0.5rem;">${topic.description}</p>
        <p class="muted"><strong>Example:</strong> ${topic.example}</p>
      `;
    }

    function renderTable() {
      els.tbody.innerHTML = "";
      if (assignments.length === 0) {
        els.tbody.innerHTML = '<tr><td colspan="4" class="muted" style="text-align:center; padding:1.5rem;">No registrations yet. Be the first!</td></tr>';
        return;
      }
      const sorted = [...assignments].sort((a, b) => a.group - b.group);
      sorted.forEach(a => {
        const topic = topics.find(t => t.id === a.topicId);
        const tr = document.createElement("tr");
        tr.innerHTML = `
          <td><strong>Group ${a.group}</strong></td>
          <td><span class="leader-name">${a.leader || "Unknown"}</span></td>
          <td>${topic ? topic.label : "Custom"}</td>
          <td>${a.subtopic || "<em class='muted'>Generic</em>"}</td>
        `;
        els.tbody.appendChild(tr);
      });
    }

    function showMsg(text, type) {
      els.msg.textContent = text;
      els.msg.className = `message ${type}`;
      setTimeout(() => { els.msg.textContent = ""; }, 5000);
    }

    // --- Events --------------------------------------------------------------
    els.group.addEventListener("change", () => {
        els.pin.value = ""; 
        renderTopicOptions();
    });
    els.topic.addEventListener("change", (e) => updateDetails(e.target.value));

    els.confirm.addEventListener("click", () => {
      const group = Number(els.group.value);
      const topicId = els.topic.value;
      const subtopic = els.subtopic.value.trim();
      const leader = els.leader.value.trim();
      const pin = els.pin.value.trim();

      if (!group) return showMsg("Please select a Group Number.", "error");
      if (!leader) return showMsg("Please enter Leader's name.", "error");
      if (!pin || pin.length < 3) return showMsg("Please set a PIN (min 3 digits).", "error");
      if (!topicId) return showMsg("Please select a Topic.", "error");
      if (topicId === 'custom' && !subtopic) return showMsg("Custom topics require a specific Title.", "error");

      const assignedMap = getAssignedMap();
      const existingAssignment = getGroupAssignment(group);
      
      if (existingAssignment && existingAssignment.pin !== pin) {
        return showMsg(`Incorrect PIN for Group ${group}.`, "error");
      }

      if (topicId !== 'custom' && assignedMap.has(topicId)) {
        const ownerGroup = assignedMap.get(topicId);
        if (ownerGroup !== group) return showMsg(`Topic taken by Group ${ownerGroup}.`, "error");
      }

      const newEntry = { group, topicId, subtopic, leader, pin }; 
      if (existingAssignment) {
        assignments.splice(assignments.indexOf(existingAssignment), 1);
        showMsg("Registration Updated!", "success");
      } else {
        showMsg("Group Registered Successfully!", "success");
      }
      
      assignments.push(newEntry);
      saveData();
      renderTopicOptions();
      renderTable();
      els.pin.value = "";
    });

    els.reset.addEventListener("click", () => {
      const pwd = prompt("Admin Password:");
      if (pwd === ADMIN_PASSWORD) {
        assignments = [];
        saveData();
        init(); 
        showMsg("System Reset Complete.", "success");
      } else if (pwd !== null) {
        alert("Wrong Password.");
      }
    });

    // Start
    init();
  </script>
</body>

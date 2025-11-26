<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Poster Topic Registration · Bachelor in Computer Science</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color-scheme: light;
      --primary: #2563eb;
      --primary-hover: #1d4ed8;
      --bg-color: #f5f5f8;
      --card-bg: #ffffff;
      --border-color: #e2e2e8;
    }
    body {
      margin: 0;
      padding: 1.5rem;
      background: var(--bg-color);
      color: #1f2937;
    }
    h1, h2, h3 { margin: 0 0 0.75rem; }
    .container {
      max-width: 1000px;
      margin: 0 auto;
      background: var(--card-bg);
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 4px 18px rgba(0,0,0,0.05);
    }
    .muted { font-size: 0.85rem; color: #6b7280; line-height: 1.5; }
    
    /* Layout */
    .grid {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 1.5rem;
      margin-top: 1rem;
      align-items: flex-start;
    }
    .card {
      background: #fafafa;
      border-radius: 10px;
      padding: 1rem 1.2rem;
      border: 1px solid var(--border-color);
    }
    .row {
      display: flex;
      gap: 1rem;
      align-items: flex-end; 
      flex-wrap: wrap;
      margin-bottom: 1rem;
    }
    .row > div { flex: 1; min-width: 140px; }

    /* Form Elements */
    label {
      display: block;
      font-size: 0.9rem;
      margin-bottom: 0.35rem;
      font-weight: 600;
      color: #374151;
    }
    select, input[type="text"], input[type="password"], button {
      width: 100%;
      padding: 0.6rem;
      font-size: 0.95rem;
      border-radius: 8px;
      border: 1px solid #c8c8d6;
      box-sizing: border-box;
      transition: border-color 0.2s;
    }
    select:focus, input:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
    }
    button {
      cursor: pointer;
      border: none;
      background: var(--primary);
      color: white;
      font-weight: 600;
      margin-top: 0.5rem;
      padding: 0.75rem;
    }
    button:hover { background: var(--primary-hover); }
    button:disabled { background: #9ca3af; cursor: not-allowed; }
    
    button.secondary {
      background: #e5e7eb;
      color: #111827;
      margin-top: 0;
      width: auto;
      padding: 0.4rem 0.8rem;
      font-size: 0.85rem;
    }
    button.secondary:hover { background: #d1d5db; }

    /* Topic Info & Status */
    .badge {
      display: inline-flex;
      padding: 0.15rem 0.6rem;
      border-radius: 999px;
      font-size: 0.75rem;
      font-weight: 600;
      vertical-align: middle;
      margin-left: 0.5rem;
    }
    .level-easy { background: #dcfce7; color: #166534; }
    .level-medium { background: #fef9c3; color: #854d0e; }
    .level-advanced { background: #fee2e2; color: #991b1b; }
    .level-custom { background: #e0e7ff; color: #3730a3; }

    .info-box {
      background: #eff6ff;
      border: 1px solid #bfdbfe;
      color: #1e40af;
      padding: 0.8rem;
      border-radius: 8px;
      font-size: 0.9rem;
      margin-top: 1rem;
      display: none; 
    }
    .info-box a { color: #1e40af; font-weight: 600; text-decoration: underline;}

    /* Table */
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 0.75rem;
      font-size: 0.9rem;
      background: #ffffff;
      border-radius: 8px;
      overflow: hidden;
      border: 1px solid var(--border-color);
    }
    th, td {
      border-bottom: 1px solid var(--border-color);
      padding: 0.6rem 0.8rem;
      text-align: left;
    }
    th { background: #f3f4f6; font-weight: 600; }
    tr:last-child td { border-bottom: none; }
    .leader-name { color: var(--primary); font-weight: 500; }

    /* Messages */
    .message { margin-top: 0.8rem; font-size: 0.95rem; font-weight: 500; }
    .message.error { color: #b91c1c; }
    .message.success { color: #166534; }

    @media (max-width: 800px) {
      .grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Poster Topic Registration</h1>
    <p class="muted">
      Group Poster Session · Bachelor in Computer Science · University of Luxembourg<br />
      <strong>Instructions:</strong> Select your group number and a topic. You must set a <strong>PIN</strong> to protect your registration. You will need this PIN to modify your choice later.
    </p>

    <div class="card">
      <h2>Step 1 · Group & Topic Selection</h2>
      
      <div class="grid">
        <div>
          <div class="row">
            <div style="flex: 0 0 120px;">
              <label for="groupSelect">Group #</label>
              <select id="groupSelect">
                <option value="">Select...</option>
              </select>
            </div>
            <div>
              <label for="leaderInput">Group Leader</label>
              <input type="text" id="leaderInput" placeholder="Full Name" />
            </div>
            <div style="flex: 0 0 100px;">
              <label for="pinInput">PIN (4-digit)</label>
              <input type="password" id="pinInput" placeholder="1234" maxlength="6" />
            </div>
          </div>

          <div style="margin-bottom: 1rem;">
            <label for="topicSelect">Select a Main Topic</label>
            <select id="topicSelect">
              <option value="">Choose a topic area...</option>
            </select>
            
            <div id="customTopicAlert" class="info-box">
              <strong>Proposing a new topic?</strong><br/>
              Please email the Teaching Assistant at 
              <a href="mailto:hongyang.li@uni.lu?subject=Poster Topic Proposal">hongyang.li@uni.lu</a> 
              to verify if your topic is suitable.<br/><br/>
              <em>If approved, enter your specific title below and confirm.</em>
            </div>
          </div>

          <div style="margin-bottom: 1rem;">
            <label for="subtopicInput">Specific Subtopic / Poster Title</label>
            <input
              type="text"
              id="subtopicInput"
              placeholder="e.g. Object Detection with YOLOv8"
            />
            <div class="muted" style="margin-top:0.25rem; font-size:0.8rem;">
              Optional for standard topics, <strong>required</strong> for custom topics.
            </div>
          </div>

          <button id="confirmBtn">Confirm / Update Registration</button>
          <div id="message" class="message"></div>
        </div>

        <div class="card" style="background: #fff; border-color:#e5e7eb;">
          <h3>Topic Description</h3>
          <div id="topicDetails" class="muted">
            <p>Please select a topic from the list to see the details, difficulty level, and requirements.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="card" style="margin-top:1.5rem;">
      <div class="row" style="justify-content: space-between; margin-bottom: 0.5rem; align-items: center;">
        <h2 style="margin-bottom:0;">Current Registrations</h2>
        <button id="resetBtn" class="secondary" type="button">Reset All (Admin)</button>
      </div>
      <p class="muted">
        Topics listed here are already taken. To change your group's topic, enter your Group # and PIN above.
      </p>
      <table>
        <thead>
          <tr>
            <th style="width:80px;">Group</th>
            <th style="width:180px;">Leader</th>
            <th>Main Topic Area</th>
            <th>Specific Title</th>
          </tr>
        </thead>
        <tbody id="assignmentsBody">
          </tbody>
      </table>
    </div>
  </div>

  <script>
    // --- Configuration -------------------------------------------------------
    const GROUP_COUNT = 12;
    const STORAGE_KEY = "uni_poster_assignments_v4"; // Using v4 (Fresh Database)
    const ADMIN_PASSWORD = "admin"; // Admin password to reset all

    // --- Data Source ---------------------------------------------------------
    const topics = [
      { id: "dl-basics", label: "Deep Learning Fundamentals", level: "easy", description: "Core concepts of Neural Networks (CNNs, MLPs) for standard classification tasks.", example: "Handwritten digit classification (MNIST) using simple CNNs." },
      { id: "nlp-sentiment", label: "NLP: Sentiment Analysis", level: "easy", description: "Processing text to determine emotion or opinion (positive/negative/neutral).", example: "Movie review classifier using RNNs or Transformers." },
      { id: "cv-classification", label: "CV: Image Classification", level: "easy", description: "Assigning labels to images (e.g., Cat vs Dog, X-Ray disease detection).", example: "Classifying plants or animals using Transfer Learning (ResNet)." },
      { id: "recommender", label: "Recommender Systems", level: "easy", description: "Algorithms that suggest items to users (movies, products, music).", example: "Collaborative filtering for movie recommendations." },
      { id: "cv-detection", label: "CV: Object Detection", level: "medium", description: "Locating and identifying multiple objects within an image.", example: "Traffic sign detection using YOLO." },
      { id: "nlp-chatbot", label: "NLP: Chatbots & Q&A", level: "medium", description: "Systems that can answer questions or hold simple conversations.", example: "Building a FAQ bot using RAG (Retrieval-Augmented Generation)." },
      { id: "time-series", label: "Time Series Forecasting", level: "medium", description: "Predicting future values based on past time-sequenced data.", example: "Stock price or weather prediction using LSTM/GRU." },
      { id: "ai-games", label: "AI for Games", level: "medium", description: "Creating agents that can play games or control NPCs.", example: "Training an agent to play Super Mario using Reinforcement Learning." },
      { id: "ai-health", label: "AI in Healthcare", level: "medium", description: "Applying ML to medical diagnostics, imaging, or records.", example: "Tumor segmentation in MRI scans." },
      { id: "ai-finance", label: "AI in FinTech", level: "medium", description: "Fraud detection, credit scoring, or algorithmic trading.", example: "Detecting credit card fraud with Anomaly Detection." },
      { id: "cybersec", label: "AI for Cybersecurity", level: "medium", description: "Using ML to detect network attacks, phishing, or malware.", example: "Email phishing detection using Natural Language Processing." },
      { id: "xai", label: "Explainable AI (XAI)", level: "medium", description: "Techniques to make 'black box' AI models interpretable to humans.", example: "Using SHAP/LIME to explain why a loan was rejected." },
      { id: "audio-ai", label: "Audio & Speech Processing", level: "medium", description: "Analyzing audio signals for recognition or classification.", example: "Speech command recognition or music genre classification." },
      { id: "ethics", label: "AI Ethics, Bias & Fairness", level: "medium", description: "Studying and mitigating bias in datasets and models.", example: "Demonstrating and fixing gender bias in hiring algorithms." },
      { id: "gen-ai", label: "Generative AI (Images/Text)", level: "advanced", description: "Models that create new content. Includes GANs, Diffusion models, and LLMs.", example: "Image generation with Stable Diffusion or text generation with GPT." },
      { id: "gnn", label: "Graph Neural Networks (GNN)", level: "advanced", description: "Deep learning on graph-structured data (social networks, molecules).", example: "Predicting chemical properties of molecules." },
      { id: "autonomous", label: "Autonomous Vehicles / Robotics", level: "advanced", description: "Perception, planning, and control systems for robots.", example: "Lane keeping and obstacle avoidance simulation." },
      { id: "federated", label: "Federated Learning", level: "advanced", description: "Training models across decentralized devices preserving privacy.", example: "Collaborative learning on mobile devices without data sharing." },
      { id: "multi-modal", label: "Multi-modal Learning", level: "advanced", description: "Learning from multiple types of data (e.g., Image + Text) simultaneously.", example: "Visual Question Answering (VQA) systems." },
      { id: "edge-ai", label: "Edge AI / TinyML", level: "advanced", description: "Optimizing and running AI models on hardware with limited resources.", example: "Real-time keyword spotting on a Raspberry Pi." },
      { id: "custom", label: "Other / Propose a custom topic", level: "custom", description: "<strong>Requires Approval:</strong> Do you have a specific research interest not listed here? Please contact TA Hongyang Li.", example: "Your specific approved research title." }
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

    // --- State Management ----------------------------------------------------
    let assignments = loadData();

    function loadData() {
      try {
        return JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
      } catch { return []; }
    }

    function saveData() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(assignments));
    }

    function getAssignedMap() {
      return new Map(assignments.map(a => [a.topicId, a.group]));
    }
    
    function getGroupAssignment(groupNum) {
      return assignments.find(a => a.group === groupNum);
    }

    // --- Rendering -----------------------------------------------------------
    function init() {
      // 1. Fill Groups
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

    function getLevelBadge(level) {
      const classes = { easy: "level-easy", medium: "level-medium", advanced: "level-advanced", custom: "level-custom" };
      const titles = { easy: "Easy", medium: "Medium", advanced: "Advanced", custom: "Approval Required" };
      return `<span class="badge ${classes[level] || ''}">${titles[level] || level}</span>`;
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

        // Mark taken topics
        if (t.id !== 'custom' && isTaken) {
          label += ` (Taken by Group ${assignedMap.get(t.id)})`;
          if (!takenByMe) opt.disabled = true;
        }

        opt.textContent = label;
        els.topic.appendChild(opt);
      });

      // Update Form State based on Group selection
      if (myAssignment) {
        // Edit Mode
        els.topic.value = myAssignment.topicId;
        els.subtopic.value = myAssignment.subtopic || "";
        els.leader.value = myAssignment.leader || "";
        els.confirm.textContent = "Update Registration";
        
        // Correctly reference the pin element
        els.pin.placeholder = "Enter PIN to edit"; 
        
        updateDetails(myAssignment.topicId);
      } else {
        // New Registration Mode
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
        if(!els.topic.value) updateDetails("");
        else updateDetails(els.topic.value);
      }
    }

    function updateDetails(topicId) {
      const topic = topics.find(t => t.id === topicId);
      
      if (topicId === 'custom') els.customAlert.style.display = "block";
      else els.customAlert.style.display = "none";

      if (!topic) {
        els.details.innerHTML = '<p class="muted">Select a topic to see details.</p>';
        return;
      }

      els.details.innerHTML = `
        <h4 style="margin-bottom:0.5rem;">${topic.label} ${getLevelBadge(topic.level)}</h4>
        <p>${topic.description}</p>
        <p><strong>Example:</strong> ${topic.example}</p>
      `;
    }

    function renderTable() {
      els.tbody.innerHTML = "";
      if (assignments.length === 0) {
        els.tbody.innerHTML = '<tr><td colspan="4" class="muted" style="text-align:center;">No registrations yet.</td></tr>';
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

    // --- Logic ---------------------------------------------------------------
    
    els.group.addEventListener("change", () => {
        els.pin.value = ""; // Clear PIN on group switch
        renderTopicOptions();
    });
    els.topic.addEventListener("change", (e) => updateDetails(e.target.value));

    els.confirm.addEventListener("click", () => {
      const group = Number(els.group.value);
      const topicId = els.topic.value;
      const subtopic = els.subtopic.value.trim();
      const leader = els.leader.value.trim();
      const pin = els.pin.value.trim();

      // Basic Validation
      if (!group) return showMsg("Please select a Group Number.", "error");
      if (!leader) return showMsg("Please enter the Group Leader's name.", "error");
      if (!pin || pin.length < 3) return showMsg("Please enter a PIN (at least 3 digits).", "error");
      if (!topicId) return showMsg("Please select a Topic.", "error");
      if (topicId === 'custom' && !subtopic) return showMsg("Custom topics require a specific Title.", "error");

      const assignedMap = getAssignedMap();
      const existingAssignment = getGroupAssignment(group);
      
      // Security Check: PIN Verification
      if (existingAssignment) {
        if (existingAssignment.pin !== pin) {
          return showMsg(`Incorrect PIN for Group ${group}. Cannot modify registration.`, "error");
        }
      }

      // Conflict Check: Topic taken by OTHERS?
      if (topicId !== 'custom' && assignedMap.has(topicId)) {
        const ownerGroup = assignedMap.get(topicId);
        if (ownerGroup !== group) {
           return showMsg(`Topic already taken by Group ${ownerGroup}.`, "error");
        }
      }

      // Update Data
      const newEntry = { group, topicId, subtopic, leader, pin }; 
      
      if (existingAssignment) {
        const idx = assignments.indexOf(existingAssignment);
        assignments.splice(idx, 1);
        showMsg(`Registration Updated for Group ${group}.`, "success");
      } else {
        showMsg(`Registered: Group ${group} with PIN protection.`, "success");
      }
      
      assignments.push(newEntry);
      saveData();
      
      renderTopicOptions();
      renderTable();
      els.pin.value = "";
    });

    els.reset.addEventListener("click", () => {
      const pwd = prompt("Enter ADMIN PASSWORD to reset all data:");
      if (pwd === ADMIN_PASSWORD) {
        assignments = [];
        saveData();
        init(); 
        showMsg("System Reset: All registrations cleared.", "success");
      } else if (pwd !== null) {
        alert("Incorrect Admin Password.");
      }
    });

    // Run
    init();

  </script>
</body>
</html>

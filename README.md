<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Poster Topic Registration · Bachelor in Computer Science · FSTM</title>
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
      align-items: center;
      flex-wrap: wrap;
      margin-bottom: 1rem;
    }
    .row > div { flex: 1; min-width: 180px; }

    /* Form Elements */
    label {
      display: block;
      font-size: 0.9rem;
      margin-bottom: 0.35rem;
      font-weight: 600;
      color: #374151;
    }
    select, input[type="text"], button {
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
      display: none; /* Hidden by default */
    }
    .info-box a { color: #1e40af; font-weight: 600; }

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
      Group Poster Session · Bachelor in Computer Science · FSTM · University of Luxembourg (2025–2026)<br />
      <strong>Instructions:</strong> Each group must register <strong>one</strong> topic. The group leader is responsible for this registration.
    </p>

    <div class="card">
      <h2>Step 1 · Group & Topic Selection</h2>
      
      <div class="grid">
        <div>
          <div class="row">
            <div>
              <label for="groupSelect">Group Number</label>
              <select id="groupSelect">
                <option value="">Select group...</option>
              </select>
            </div>
            <div>
              <label for="leaderInput">Group Leader (Full Name)</label>
              <input type="text" id="leaderInput" placeholder="e.g. Marc Smith" />
            </div>
          </div>

          <div style="margin-bottom: 1rem;">
            <label for="topicSelect">Select a Main Topic</label>
            <select id="topicSelect">
              <option value="">Choose a topic area...</option>
            </select>
            
            <div id="customTopicAlert" class="info-box">
              <strong>Proposing a new topic?</strong><br/>
              Please email the course coordinator at 
              <a href="mailto:hongyang.li@uni.lu?subject=Poster Topic Proposal">professor@uni.lu</a> 
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

          <button id="confirmBtn">Confirm Registration</button>
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
      <div class="row" style="justify-content: space-between; margin-bottom: 0.5rem;">
        <h2 style="margin-bottom:0;">Current Registrations</h2>
        <button id="resetBtn" class="secondary" type="button">Reset All (Admin)</button>
      </div>
      <p class="muted">
        Topics listed here are already taken and cannot be selected by other groups.
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
    const STORAGE_KEY = "uni_poster_assignments_v2"; // Changed key version

    // --- Data Source ---------------------------------------------------------
    const topics = [
      {
        id: "deep-learning",
        label: "Deep Learning Fundamentals",
        level: "easy",
        description: "Core concepts of Neural Networks (CNNs, MLPs) for classification tasks.",
        example: "Image classification using ResNet-50."
      },
      {
        id: "nlp",
        label: "Natural Language Processing (NLP)",
        level: "easy",
        description: "Processing text data for analysis, translation, or generation.",
        example: "Sentiment analysis on movie reviews using BERT."
      },
      {
        id: "cv",
        label: "Computer Vision",
        level: "easy",
        description: "Enabling computers to identify and process images/video.",
        example: "Real-time face mask detection."
      },
      {
        id: "xai",
        label: "Explainable AI (XAI)",
        level: "easy",
        description: "Making black-box models transparent and interpretable.",
        example: "Visualizing CNN decisions with Grad-CAM."
      },
      {
        id: "ai-health",
        label: "AI in Healthcare",
        level: "medium",
        description: "Applying ML to medical diagnostics, imaging, or records.",
        example: "Predicting diabetes onset using patient records."
      },
      {
        id: "ai-finance",
        label: "AI in Finance (FinTech)",
        level: "medium",
        description: "Fraud detection, stock prediction, or algorithmic trading.",
        example: "Credit card fraud detection using Isolation Forests."
      },
      {
        id: "autonomous",
        label: "Autonomous Systems",
        level: "medium",
        description: "Perception and control for self-driving cars or drones.",
        example: "Lane line detection for autonomous driving."
      },
      {
        id: "rl",
        label: "Reinforcement Learning",
        level: "medium",
        description: "Agents learning actions through rewards and penalties.",
        example: "Training an agent to play Snake via Q-Learning."
      },
      {
        id: "cybersec",
        label: "AI for Cybersecurity",
        level: "medium",
        description: "Detecting network intrusions or malware with AI.",
        example: "Phishing URL detection using Random Forest."
      },
      {
        id: "gen-ai",
        label: "Generative AI & LLMs",
        level: "advanced",
        description: "Models that generate new content (text, images, code).",
        example: "Fine-tuning a small LLM for specific code generation."
      },
      {
        id: "federated",
        label: "Federated Learning",
        level: "advanced",
        description: "Decentralized training preserving data privacy.",
        example: "Training on distributed client data without sharing."
      },
      {
        id: "edge-ai",
        label: "Edge AI / IoT",
        level: "advanced",
        description: "Deploying efficient models on microcontrollers/Raspberry Pi.",
        example: "Voice command recognition on low-power devices."
      },
      // The Custom Option
      {
        id: "custom",
        label: "Other / Propose a custom topic",
        level: "custom",
        description: "<strong>Requires Approval:</strong> Do you have a specific research interest not listed here? Please contact the supervisor.",
        example: "Your specific approved research title."
      }
    ];

    // --- DOM Elements --------------------------------------------------------
    const els = {
      group: document.getElementById("groupSelect"),
      leader: document.getElementById("leaderInput"),
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
      // Returns Map<TopicID, GroupNum>
      return new Map(assignments.map(a => [a.topicId, a.group]));
    }
    
    function getGroupAssignment(groupNum) {
      return assignments.find(a => a.group === groupNum);
    }

    // --- Rendering -----------------------------------------------------------
    function init() {
      // 1. Fill Groups
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
      const classes = {
        easy: "level-easy",
        medium: "level-medium",
        advanced: "level-advanced",
        custom: "level-custom"
      };
      const titles = {
        easy: "Level: Easy",
        medium: "Level: Medium",
        advanced: "Level: Advanced",
        custom: "Approval Required"
      };
      return `<span class="badge ${classes[level] || ''}">${titles[level] || level}</span>`;
    }

    function renderTopicOptions() {
      const assignedMap = getAssignedMap();
      const currentGroup = Number(els.group.value);
      const myAssignment = currentGroup ? getGroupAssignment(currentGroup) : null;
      
      // Save current selection to restore if possible, else reset
      const currentSelection = els.topic.value; 

      els.topic.innerHTML = '<option value="">Choose a topic area...</option>';

      topics.forEach(t => {
        const opt = document.createElement("option");
        opt.value = t.id;
        
        let label = t.label;
        const isTaken = assignedMap.has(t.id);
        const takenByMe = myAssignment && myAssignment.topicId === t.id;

        // Custom topics can theoretically be taken by multiple groups if different titles,
        // but for simplicity, let's allow "custom" to be selected multiple times 
        // OR strictly limit it. Here we allow "custom" to be re-selected because 
        // different groups might have different custom topics.
        // HOWEVER, standard topics are exclusive.
        
        if (t.id !== 'custom' && isTaken) {
          label += ` (Taken by Group ${assignedMap.get(t.id)})`;
          if (!takenByMe) opt.disabled = true;
        }

        opt.textContent = label;
        els.topic.appendChild(opt);
      });

      // Restore selection if valid
      if (myAssignment) {
        els.topic.value = myAssignment.topicId;
        els.subtopic.value = myAssignment.subtopic || "";
        els.leader.value = myAssignment.leader || "";
        updateDetails(myAssignment.topicId);
      } else {
        els.topic.value = currentSelection; // keep selection if switching groups (unless invalid)
        if (!currentSelection) {
            els.leader.value = "";
            els.subtopic.value = "";
        }
      }
      
      // Trigger detail update to handle the "Custom" box visibility
      updateDetails(els.topic.value);
    }

    function updateDetails(topicId) {
      const topic = topics.find(t => t.id === topicId);
      
      // Handle Custom Alert visibility
      if (topicId === 'custom') {
        els.customAlert.style.display = "block";
      } else {
        els.customAlert.style.display = "none";
      }

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

      // Sort by group number
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
    
    // Watch for changes
    els.group.addEventListener("change", renderTopicOptions);
    els.topic.addEventListener("change", (e) => updateDetails(e.target.value));

    // Confirm Action
    els.confirm.addEventListener("click", () => {
      const group = Number(els.group.value);
      const topicId = els.topic.value;
      const subtopic = els.subtopic.value.trim();
      const leader = els.leader.value.trim();

      // Validation
      if (!group) return showMsg("Please select a Group Number.", "error");
      if (!leader) return showMsg("Please enter the Group Leader's name.", "error");
      if (!topicId) return showMsg("Please select a Topic.", "error");
      
      if (topicId === 'custom' && !subtopic) {
        return showMsg("For custom topics, you must enter the specific Title approved by the teacher.", "error");
      }

      // Check double booking (server-side usually, but local here)
      const assignedMap = getAssignedMap();
      const existingAssignment = getGroupAssignment(group);
      
      // If topic is taken by SOMEONE ELSE (and not custom)
      if (topicId !== 'custom' && assignedMap.has(topicId)) {
        const ownerGroup = assignedMap.get(topicId);
        if (ownerGroup !== group) {
            return showMsg(`Topic already taken by Group ${ownerGroup}.`, "error");
        }
      }

      // Save
      const newEntry = { group, topicId, subtopic, leader };
      
      // Remove old entry for this group if exists
      if (existingAssignment) {
        const idx = assignments.indexOf(existingAssignment);
        assignments.splice(idx, 1);
      }
      
      assignments.push(newEntry);
      saveData();
      
      renderTopicOptions();
      renderTable();
      showMsg(`Success! Group ${group} registered for "${topicId === 'custom' ? subtopic : topics.find(t=>t.id===topicId).label}".`, "success");
    });

    // Reset Action
    els.reset.addEventListener("click", () => {
      if(confirm("Are you sure you want to reset ALL registrations?")) {
        assignments = [];
        saveData();
        init(); // re-init to clear everything
        showMsg("All data reset.", "success");
      }
    });

    // Run
    init();

  </script>
</body>
</html>

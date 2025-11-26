、<html lang="en">
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
    h1, h2, h3, h4 { margin: 0 0 0.75rem; }
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
    
    button.secondary {
      background: #e5e7eb;
      color: #111827;
      margin-top: 0;
      width: auto;
      padding: 0.4rem 0.8rem;
      font-size: 0.85rem;
    }
    button.secondary:hover { background: #d1d5db; }

    /* Badges & Info */
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
      Group Poster Session · Bachelor in Computer Science · FSTM · University of Luxembourg<br />
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
              Please email the poster coordinator at 
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
              placeholder="e.g. Real-time Object Detection with YOLOv8"
            />
            <div class="muted" style="margin-top:0.25rem; font-size:0.8rem;">
              Recommended for standard topics, <strong>required</strong> for custom topics.
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
        Topics listed here are already taken and cannot be selected by other groups (except Custom topics).
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
    const GROUP_COUNT = 15; // Increased group capacity
    const STORAGE_KEY = "uni_poster_assignments_v3"; // New key for fresh data

    // --- Extended Data Source (Grouped by Category) --------------------------
    const topics = [
      // 1. Artificial Intelligence & ML
      {
        id: "deep-learning", category: "Artificial Intelligence", label: "Deep Learning Fundamentals", level: "easy",
        description: "Core concepts of Neural Networks (CNNs, RNNs) for classification.",
        example: "Image classification with ResNet."
      },
      {
        id: "nlp", category: "Artificial Intelligence", label: "Natural Language Processing (NLP)", level: "easy",
        description: "Processing text data for translation, sentiment, or chatbots.",
        example: "Sentiment analysis on Twitter data."
      },
      {
        id: "cv", category: "Artificial Intelligence", label: "Computer Vision", level: "easy",
        description: "Enabling computers to 'see' and interpret images/video.",
        example: "Face mask detection using OpenCV and CNN."
      },
      {
        id: "gen-ai", category: "Artificial Intelligence", label: "Generative AI & LLMs", level: "medium",
        description: "Models that generate text, images, or code (GPT, Stable Diffusion).",
        example: "Using LLMs for code generation."
      },
      {
        id: "rl", category: "Artificial Intelligence", label: "Reinforcement Learning", level: "medium",
        description: "Agents learning actions through rewards and penalties (Game AI).",
        example: "Training an agent to play Super Mario."
      },
      {
        id: "xai", category: "Artificial Intelligence", label: "Explainable AI (XAI)", level: "medium",
        description: "Making black-box models transparent and interpretable.",
        example: "Visualizing model decisions with SHAP/LIME."
      },
      {
        id: "ai-ethics", category: "Artificial Intelligence", label: "AI Ethics & Bias", level: "medium",
        description: "Studying fairness, bias, and ethical implications of AI systems.",
        example: "Detecting gender bias in hiring algorithms."
      },

      // 2. Systems, Cloud & IoT
      {
        id: "cloud-comp", category: "Systems & IoT", label: "Cloud Computing Architectures", level: "easy",
        description: "Serverless computing, virtualization, and cloud services.",
        example: "Comparing AWS Lambda vs. Azure Functions."
      },
      {
        id: "iot", category: "Systems & IoT", label: "Internet of Things (IoT)", level: "easy",
        description: "Connecting physical devices to the internet for data collection.",
        example: "Smart home automation system using MQTT."
      },
      {
        id: "edge-ai", category: "Systems & IoT", label: "Edge AI / Embedded AI", level: "advanced",
        description: "Running AI models on resource-constrained devices (Raspberry Pi).",
        example: "Real-time voice recognition on a microcontroller."
      },
      {
        id: "green-it", category: "Systems & IoT", label: "Green IT & Sustainable Computing", level: "medium",
        description: "Reducing energy consumption in data centers and software.",
        example: "Optimizing code for energy efficiency."
      },
      {
        id: "5g-6g", category: "Systems & IoT", label: "5G/6G Networks", level: "advanced",
        description: "Next-gen telecommunications and their impact on CS applications.",
        example: "Low-latency applications enabled by 5G."
      },
      {
        id: "robotics", category: "Systems & IoT", label: "Robotics & Automation", level: "medium",
        description: "Software for robot perception, planning, and control.",
        example: "Path planning algorithms for autonomous rovers."
      },

      // 3. Security & Blockchain
      {
        id: "cybersec-net", category: "Security & Blockchain", label: "Network Security", level: "easy",
        description: "Protecting networks from intrusions, DDoS, and malware.",
        example: "Analyzing network traffic for intrusion detection."
      },
      {
        id: "blockchain", category: "Security & Blockchain", label: "Blockchain & Smart Contracts", level: "medium",
        description: "Decentralized ledgers and automated contract execution.",
        example: "Building a voting system on Ethereum."
      },
      {
        id: "cryptography", category: "Security & Blockchain", label: "Applied Cryptography", level: "advanced",
        description: "Encryption methods, zero-knowledge proofs, and secure comms.",
        example: "Implementing End-to-End encryption for a chat app."
      },
      {
        id: "privacy-ai", category: "Security & Blockchain", label: "Privacy-Preserving AI", level: "advanced",
        description: "Federated Learning, Differential Privacy.",
        example: "Training models without accessing raw user data."
      },

      // 4. Software Engineering & Web
      {
        id: "devops", category: "Software Engineering", label: "DevOps & CI/CD", level: "medium",
        description: "Automating software delivery and infrastructure changes.",
        example: "Building a complete CI/CD pipeline with Docker/Jenkins."
      },
      {
        id: "microservices", category: "Software Engineering", label: "Microservices Architecture", level: "medium",
        description: "Breaking applications into small, independent services.",
        example: "Monolith vs Microservices: A performance comparison."
      },
      {
        id: "web-assembly", category: "Software Engineering", label: "WebAssembly (Wasm)", level: "advanced",
        description: "Running high-performance code (C++, Rust) in the browser.",
        example: "Porting a game engine to the web using Wasm."
      },
      {
        id: "testing", category: "Software Engineering", label: "Software Testing & QA", level: "easy",
        description: "Automated testing, fuzzing, and quality assurance strategies.",
        example: "Automated UI testing with Selenium/Playwright."
      },

      // 5. Graphics & Interactive
      {
        id: "vr-ar", category: "Graphics & HCI", label: "VR / AR (Extended Reality)", level: "medium",
        description: "Virtual and Augmented Reality applications and development.",
        example: "Building an educational AR app for mobile."
      },
      {
        id: "game-dev", category: "Graphics & HCI", label: "Game Development Algorithms", level: "medium",
        description: "Physics engines, procedural generation, or game AI.",
        example: "Procedural terrain generation using Perlin Noise."
      },
      {
        id: "hci", category: "Graphics & HCI", label: "Human-Computer Interaction", level: "easy",
        description: "Improving user experience and interface design accessibility.",
        example: "Eye-tracking interface for accessibility."
      },

      // 6. Data & Theory
      {
        id: "big-data", category: "Data & Theory", label: "Big Data Analytics", level: "medium",
        description: "Processing massive datasets (Hadoop, Spark).",
        example: "Real-time stream processing with Apache Kafka."
      },
      {
        id: "bioinformatics", category: "Data & Theory", label: "Bioinformatics", level: "advanced",
        description: "Computational methods for analyzing biological data (DNA).",
        example: "Sequence alignment algorithms."
      },
      {
        id: "quantum", category: "Data & Theory", label: "Quantum Computing Basics", level: "advanced",
        description: "Introduction to qubits, superposition and quantum algorithms.",
        example: "Simulating Grover's Algorithm."
      },

      // 7. Custom
      {
        id: "custom", category: "Other", label: "Other / Propose a custom topic", level: "custom",
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
        easy: "level-easy", medium: "level-medium", advanced: "level-advanced", custom: "level-custom"
      };
      const titles = {
        easy: "Level: Easy", medium: "Level: Medium", advanced: "Level: Advanced", custom: "Approval Required"
      };
      return `<span class="badge ${classes[level] || ''}">${titles[level] || level}</span>`;
    }

    function renderTopicOptions() {
      const assignedMap = getAssignedMap();
      const currentGroup = Number(els.group.value);
      const myAssignment = currentGroup ? getGroupAssignment(currentGroup) : null;
      
      const currentSelection = els.topic.value; 

      els.topic.innerHTML = '<option value="">Choose a topic area...</option>';

      // Group topics by category
      const categories = {};
      topics.forEach(t => {
        if (!categories[t.category]) categories[t.category] = [];
        categories[t.category].push(t);
      });

      // Render Optgroups
      for (const [catName, catTopics] of Object.entries(categories)) {
        const groupEl = document.createElement("optgroup");
        groupEl.label = catName;
        
        catTopics.forEach(t => {
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
            groupEl.appendChild(opt);
        });
        els.topic.appendChild(groupEl);
      }

      // Restore state
      if (myAssignment) {
        els.topic.value = myAssignment.topicId;
        els.subtopic.value = myAssignment.subtopic || "";
        els.leader.value = myAssignment.leader || "";
        updateDetails(myAssignment.topicId);
      } else {
        els.topic.value = currentSelection;
        if (!currentSelection) {
            els.leader.value = "";
            els.subtopic.value = "";
            els.details.innerHTML = '<p class="muted">Select a topic to see details.</p>';
        }
      }
      if (els.topic.value) updateDetails(els.topic.value);
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
        <h4 style="margin-bottom:0.5rem;">${topic.label}</h4>
        <div style="margin-bottom:0.5rem;">${getLevelBadge(topic.level)} <span class="badge" style="background:#f3f4f6; color:#4b5563;">${topic.category}</span></div>
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
    els.group.addEventListener("change", renderTopicOptions);
    els.topic.addEventListener("change", (e) => updateDetails(e.target.value));

    els.confirm.addEventListener("click", () => {
      const group = Number(els.group.value);
      const topicId = els.topic.value;
      const subtopic = els.subtopic.value.trim();
      const leader = els.leader.value.trim();

      if (!group) return showMsg("Please select a Group Number.", "error");
      if (!leader) return showMsg("Please enter the Group Leader's name.", "error");
      if (!topicId) return showMsg("Please select a Topic.", "error");
      
      if (topicId === 'custom' && !subtopic) {
        return showMsg("For custom topics, you must enter the specific Title.", "error");
      }

      const assignedMap = getAssignedMap();
      const existingAssignment = getGroupAssignment(group);
      
      if (topicId !== 'custom' && assignedMap.has(topicId)) {
        const ownerGroup = assignedMap.get(topicId);
        if (ownerGroup !== group) {
            return showMsg(`Topic already taken by Group ${ownerGroup}.`, "error");
        }
      }

      const newEntry = { group, topicId, subtopic, leader };
      if (existingAssignment) assignments.splice(assignments.indexOf(existingAssignment), 1);
      
      assignments.push(newEntry);
      saveData();
      
      renderTopicOptions();
      renderTable();
      showMsg(`Success! Group ${group} registered.`, "success");
    });

    els.reset.addEventListener("click", () => {
      if(confirm("Reset ALL registrations?")) {
        assignments = [];
        saveData();
        init();
        showMsg("All data reset.", "success");
      }
    });

    init();
  </script>
</body>
</html>

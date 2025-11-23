<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Poster Topic Registration</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color-scheme: light;
    }
    body {
      margin: 0;
      padding: 1.5rem;
      background: #f5f5f8;
    }
    h1, h2, h3 {
      margin: 0 0 0.75rem;
    }
    .container {
      max-width: 1000px;
      margin: 0 auto;
      background: #ffffff;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 4px 18px rgba(0,0,0,0.05);
    }
    .grid {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 1.25rem;
      margin-top: 1rem;
      align-items: flex-start;
    }
    .card {
      background: #fafafa;
      border-radius: 10px;
      padding: 1rem 1.2rem;
      border: 1px solid #e2e2e8;
    }
    label {
      display: block;
      font-size: 0.9rem;
      margin-bottom: 0.25rem;
      font-weight: 600;
    }
    select, input[type="text"], button {
      width: 100%;
      padding: 0.5rem 0.6rem;
      font-size: 0.95rem;
      border-radius: 8px;
      border: 1px solid #c8c8d6;
      box-sizing: border-box;
    }
    select:disabled {
      background: #f0f0f5;
    }
    button {
      cursor: pointer;
      border: none;
      background: #2563eb;
      color: white;
      font-weight: 600;
      margin-top: 0.6rem;
    }
    button:hover {
      background: #1d4ed8;
    }
    button.secondary {
      background: #e5e7eb;
      color: #111827;
      margin-top: 0;
    }
    button.secondary:hover {
      background: #d1d5db;
    }
    .row {
      display: flex;
      gap: 0.75rem;
      align-items: center;
      flex-wrap: wrap;
      margin-bottom: 0.5rem;
    }
    .row > div {
      flex: 1;
      min-width: 180px;
    }
    .badge {
      display: inline-flex;
      padding: 0.1rem 0.5rem;
      border-radius: 999px;
      font-size: 0.75rem;
      font-weight: 600;
      vertical-align: middle;
    }
    .level-easy { background: #dcfce7; color: #166534; }
    .level-medium { background: #fef9c3; color: #854d0e; }
    .level-advanced { background: #fee2e2; color: #991b1b; }
    .muted {
      font-size: 0.85rem;
      color: #6b7280;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 0.75rem;
      font-size: 0.9rem;
      background: #ffffff;
      border-radius: 10px;
      overflow: hidden;
    }
    th, td {
      border: 1px solid #e5e7eb;
      padding: 0.5rem 0.6rem;
      text-align: left;
    }
    th {
      background: #f3f4f6;
      font-weight: 600;
    }
    .taken {
      color: #9ca3af;
      font-style: italic;
      font-size: 0.85rem;
    }
    .message {
      margin-top: 0.5rem;
      font-size: 0.9rem;
    }
    .message.error { color: #b91c1c; }
    .message.success { color: #166534; }
    @media (max-width: 800px) {
      .grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Poster Topic Registration</h1>
    <p class="muted">
      Bachelor in Computer Science · Group Poster Session<br />
      One representative per group should register the topic here.
    </p>

    <div class="card">
      <h2>Step 1 · Choose Group and Topic</h2>
      <p class="muted">
        Each topic can be used by <strong>only one group</strong>. After you confirm,
        this topic will no longer be available for other groups.
      </p>

      <div class="grid">
        <!-- Left: Form -->
        <div>
          <div class="row">
            <div>
              <label for="groupSelect">Group number</label>
              <select id="groupSelect">
                <option value="">Select your group…</option>
              </select>
            </div>
            <div>
              <label for="topicSelect">Poster topic (main area)</label>
              <select id="topicSelect">
                <option value="">Select a topic…</option>
              </select>
            </div>
          </div>

          <div>
            <label for="subtopicInput">Specific subtopic / poster title (optional but recommended)</label>
            <input
              type="text"
              id="subtopicInput"
              placeholder="e.g. Object Detection with YOLO and DETR"
            />
          </div>

          <button id="confirmBtn">Confirm Selection</button>
          <div id="message" class="message"></div>
        </div>

        <!-- Right: Topic details -->
        <div class="card">
          <h3>Topic details</h3>
          <div id="topicDetails" class="muted">
            Select a topic to see description, example subtopic, and difficulty level.
          </div>
        </div>
      </div>
    </div>

    <div class="card" style="margin-top:1.5rem;">
      <div class="row" style="justify-content: space-between;">
        <h2 style="margin-bottom:0;">Current registrations</h2>
        <button id="resetBtn" class="secondary" type="button">Reset all (teacher only)</button>
      </div>
      <p class="muted">
        Check here which group has already taken which topic. Topics in the list above will be disabled once chosen.
      </p>
      <table>
        <thead>
          <tr>
            <th style="width:70px;">Group</th>
            <th style="width:220px;">Main topic</th>
            <th>Specific subtopic / poster title</th>
          </tr>
        </thead>
        <tbody id="assignmentsBody">
          <!-- Filled by JS -->
        </tbody>
      </table>
    </div>
  </div>

  <script>
    // --- Topic data ----------------------------------------------------------
    const topics = [
      {
        id: "deep-learning",
        label: "Deep Learning and Neural Networks",
        level: "easy",
        description: "Basic ideas of deep learning, focusing on convolutional or feed-forward networks.",
        example: "Image classification with CNNs (LeNet, AlexNet, ResNet)."
      },
      {
        id: "nlp",
        label: "Natural Language Processing (NLP)",
        level: "easy",
        description: "Models that process text for classification, translation, question answering, etc.",
        example: "Sentiment analysis with BERT or other pre-trained language models."
      },
      {
        id: "cv",
        label: "Computer Vision",
        level: "easy",
        description: "Techniques that allow computers to understand images or videos.",
        example: "Object detection using YOLO and/or DETR."
      },
      {
        id: "xai",
        label: "Explainable AI",
        level: "easy",
        description: "Methods for explaining machine learning model predictions.",
        example: "Using LIME or SHAP to explain decisions of a classifier."
      },
      {
        id: "ai-health",
        label: "AI in Healthcare",
        level: "medium",
        description: "AI methods applied to medical data such as images or electronic health records.",
        example: "Medical image segmentation for tumor detection."
      },
      {
        id: "ai-finance",
        label: "AI in Finance",
        level: "medium",
        description: "Machine learning models for fraud detection, credit scoring, or forecasting.",
        example: "Fraud detection using anomaly detection methods."
      },
      {
        id: "ai-smart-cities",
        label: "AI for Smart Cities",
        level: "medium",
        description: "Using AI for traffic prediction, energy optimization, and urban planning.",
        example: "Traffic flow prediction with time series or graph neural networks."
      },
      {
        id: "autonomous-vehicles",
        label: "Autonomous Vehicles",
        level: "medium",
        description: "Perception and decision-making systems used for self-driving cars.",
        example: "Perception pipeline for lane detection and object detection."
      },
      {
        id: "reinforcement-learning",
        label: "Reinforcement Learning",
        level: "medium",
        description: "Learning by trial and error through rewards and penalties.",
        example: "Deep Q-learning for playing simple games."
      },
      {
        id: "cybersecurity-ai",
        label: "Cybersecurity with AI",
        level: "medium",
        description: "Using machine learning to detect attacks, malware, or intrusions.",
        example: "Intrusion detection using classification models on network traffic."
      },
      {
        id: "federated-learning",
        label: "Federated Learning",
        level: "advanced",
        description: "Training models across many devices without centralizing the data.",
        example: "Federated learning for training a shared model on mobile phones."
      },
      {
        id: "blockchain-ai",
        label: "Blockchain Technology in AI",
        level: "advanced",
        description: "Using blockchain to secure, audit, or coordinate AI systems.",
        example: "Managing model updates using blockchain-based logs."
      },
      {
        id: "edge-ai",
        label: "AI for Edge Computing",
        level: "advanced",
        description: "Running AI models on small devices with limited resources.",
        example: "Model compression and quantization for edge devices."
      },
      {
        id: "data-privacy-ai",
        label: "Data Privacy in AI",
        level: "advanced",
        description: "Techniques for protecting user data in AI systems.",
        example: "Differential privacy or anonymization in machine learning."
      },
      {
        id: "quantum-ai",
        label: "Quantum Computing and AI",
        level: "advanced",
        description: "Exploring how quantum computing can speed up or change AI.",
        example: "High-level overview of quantum machine learning algorithms."
      },
      {
        id: "robotics-ai",
        label: "Robotics and AI",
        level: "medium",
        description: "Combining perception, planning, and control for autonomous robots.",
        example: "Robot navigation using SLAM and reinforcement learning."
      }
    ];

    // --- DOM elements --------------------------------------------------------
    const groupSelect = document.getElementById("groupSelect");
    const topicSelect = document.getElementById("topicSelect");
    const subtopicInput = document.getElementById("subtopicInput");
    const topicDetails = document.getElementById("topicDetails");
    const confirmBtn = document.getElementById("confirmBtn");
    const resetBtn = document.getElementById("resetBtn");
    const messageEl = document.getElementById("message");
    const assignmentsBody = document.getElementById("assignmentsBody");

    // --- State & storage -----------------------------------------------------
    const GROUP_COUNT = 12;
    const STORAGE_KEY = "posterTopicAssignments_v1";

    let assignments = loadAssignments(); // { group: number, topicId: string, subtopic: string }[]

    function loadAssignments() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        if (!raw) return [];
        const parsed = JSON.parse(raw);
        if (Array.isArray(parsed)) return parsed;
      } catch (e) {
        console.warn("Failed to parse assignments from storage", e);
      }
      return [];
    }

    function saveAssignments() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(assignments));
    }

    // --- Helpers -------------------------------------------------------------
    function levelBadge(level) {
      if (level === "easy") {
        return '<span class="badge level-easy">Level: Easy</span>';
      } else if (level === "medium") {
        return '<span class="badge level-medium">Level: Medium</span>';
      } else {
        return '<span class="badge level-advanced">Level: Advanced</span>';
      }
    }

    function getAssignedTopicMap() {
      const map = new Map();
      for (const a of assignments) {
        map.set(a.topicId, a.group);
      }
      return map;
    }

    function getAssignmentForGroup(group) {
      return assignments.find(a => a.group === group) || null;
    }

    // --- UI rendering --------------------------------------------------------
    function initGroups() {
      // Fill group select 1..12
      for (let g = 1; g <= GROUP_COUNT; g++) {
        const opt = document.createElement("option");
        opt.value = String(g);
        opt.textContent = `Group ${g}`;
        groupSelect.appendChild(opt);
      }
    }

    function renderTopicOptions() {
      const assignedMap = getAssignedTopicMap();
      const currentGroup = groupSelect.value ? Number(groupSelect.value) : null;
      const currentGroupAssignment = currentGroup ? getAssignmentForGroup(currentGroup) : null;

      // Reset options
      topicSelect.innerHTML = "";
      const placeholder = document.createElement("option");
      placeholder.value = "";
      placeholder.textContent = "Select a topic…";
      topicSelect.appendChild(placeholder);

      topics.forEach(t => {
        const opt = document.createElement("option");
        opt.value = t.id;

        if (assignedMap.has(t.id)) {
          const takenBy = assignedMap.get(t.id);
          opt.textContent = `${t.label} (taken by Group ${takenBy})`;

          // If this topic is already assigned to THIS group, keep it selectable,
          // otherwise disable.
          if (!currentGroupAssignment || currentGroupAssignment.topicId !== t.id) {
            opt.disabled = true;
          }
        } else {
          opt.textContent = t.label;
        }

        topicSelect.appendChild(opt);
      });

      // If current group already has an assignment, auto-select it
      if (currentGroupAssignment) {
        topicSelect.value = currentGroupAssignment.topicId;
        subtopicInput.value = currentGroupAssignment.subtopic || "";
        updateTopicDetails(currentGroupAssignment.topicId);
      } else {
        topicSelect.value = "";
        subtopicInput.value = "";
        topicDetails.innerHTML = 'Select a topic to see description, example subtopic, and difficulty level.';
      }
    }

    function renderAssignmentsTable() {
      assignmentsBody.innerHTML = "";
      if (assignments.length === 0) {
        const tr = document.createElement("tr");
        const td = document.createElement("td");
        td.colSpan = 3;
        td.className = "muted";
        td.textContent = "No registrations yet.";
        tr.appendChild(td);
        assignmentsBody.appendChild(tr);
        return;
      }

      const sorted = [...assignments].sort((a, b) => a.group - b.group);

      sorted.forEach(a => {
        const tr = document.createElement("tr");

        const tdGroup = document.createElement("td");
        tdGroup.textContent = `Group ${a.group}`;
        tr.appendChild(tdGroup);

        const topic = topics.find(t => t.id === a.topicId);
        const tdTopic = document.createElement("td");
        tdTopic.textContent = topic ? topic.label : a.topicId;
        tr.appendChild(tdTopic);

        const tdSub = document.createElement("td");
        tdSub.textContent = a.subtopic || "";
        tr.appendChild(tdSub);

        assignmentsBody.appendChild(tr);
      });
    }

    function updateTopicDetails(topicId) {
      const topic = topics.find(t => t.id === topicId);
      if (!topic) {
        topicDetails.innerHTML = 'Select a topic to see description, example subtopic, and difficulty level.';
        return;
      }
      topicDetails.innerHTML = `
        <p><strong>${topic.label}</strong> ${levelBadge(topic.level)}</p>
        <p>${topic.description}</p>
        <p><strong>Example subtopic:</strong><br>${topic.example}</p>
        <p class="muted">
          Your group should:
          <br>· Read at least 3 related papers
          <br>· Understand the main methods and comparisons
          <br>· Design a clear poster based on this area
        </p>
      `;
    }

    function showMessage(text, type) {
      messageEl.textContent = text;
      messageEl.className = "message " + (type || "");
    }

    // --- Event handlers ------------------------------------------------------
    groupSelect.addEventListener("change", () => {
      showMessage("", "");
      renderTopicOptions();
    });

    topicSelect.addEventListener("change", () => {
      const topicId = topicSelect.value;
      updateTopicDetails(topicId);
      showMessage("", "");
    });

    confirmBtn.addEventListener("click", () => {
      const groupVal = groupSelect.value;
      const topicVal = topicSelect.value;
      const subtopicVal = subtopicInput.value.trim();

      if (!groupVal) {
        showMessage("Please select your group number.", "error");
        return;
      }
      if (!topicVal) {
        showMessage("Please select a topic.", "error");
        return;
      }

      const group = Number(groupVal);
      const assignedMap = getAssignedTopicMap();
      const existingForGroup = getAssignmentForGroup(group);
      const takenBy = assignedMap.get(topicVal);

      // If topic is taken by another group, prevent
      if (takenBy && (!existingForGroup || existingForGroup.topicId !== topicVal)) {
        showMessage(`This topic is already taken by Group ${takenBy}. Please choose another topic.`, "error");
        renderTopicOptions();
        return;
      }

      // Update or add assignment
      if (existingForGroup) {
        existingForGroup.topicId = topicVal;
        existingForGroup.subtopic = subtopicVal;
      } else {
        assignments.push({
          group,
          topicId: topicVal,
          subtopic: subtopicVal
        });
      }

      saveAssignments();
      renderTopicOptions();
      renderAssignmentsTable();
      const topic = topics.find(t => t.id === topicVal);
      showMessage(`Saved: Group ${group} → ${topic ? topic.label : topicVal}`, "success");
    });

    resetBtn.addEventListener("click", () => {
      if (!confirm("Reset all registrations? This will clear all stored data.")) return;
      assignments = [];
      saveAssignments();
      renderTopicOptions();
      renderAssignmentsTable();
      showMessage("All registrations have been reset.", "success");
    });

    // --- Init ---------------------------------------------------------------
    initGroups();
    renderTopicOptions();
    renderAssignmentsTable();
  </script>
</body>
</html>

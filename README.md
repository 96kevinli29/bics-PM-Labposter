<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Poster Topic Registration · Bachelor in Computer Science · FSTM · University of Luxembourg (2025–2026)</title>
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
    .header {
      text-align: center;
      margin-bottom: 1.5rem;
    }
    .header .uni {
      font-size: 1.1rem;
      font-weight: 500;
      color: #374151;
    }
    .header .course {
      font-size: 1.35rem;
      font-weight: 700;
      color: #111827;
      margin-top: 0.25rem;
    }
    .header .year {
      font-size: 1rem;
      font-weight: 500;
      color: #6b7280;
      margin-top: 0.2rem;
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
      border-radius: 8px;
      padding: 0.55rem;
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
  <div class="header">
    <div class="uni">Bachelor in Computer Science · FSTM</div>
    <div class="course">University of Luxembourg</div>
    <div class="year">2025–2026 · Poster Topic Registration</div>
  </div>

  <div class="container">
    <h1>Poster Topic Registration</h1>
    <p class="muted">
      One representative per group should register the topic here.<br>
      Each topic can be selected by <strong>only one group</strong>.
    </p>

    <div class="card">
      <h2>Step 1 · Choose Group and Topic</h2>
      <p class="muted">
        After you confirm your choice, the topic becomes unavailable for other groups.
      </p>

      <div class="grid">
        <!-- Left column: form -->
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
            <label for="subtopicInput">Specific subtopic (poster title)</label>
            <input
              type="text"
              id="subtopicInput"
              placeholder="e.g. Object Detection with YOLO and DETR"
            />
          </div>

          <button id="confirmBtn">Confirm Selection</button>
          <div id="message" class="message"></div>
        </div>

        <!-- Right column: topic details -->
        <div class="card">
          <h3>Topic details</h3>
          <div id="topicDetails" class="muted">
            Select a topic to see description, difficulty, and example subtopic.
          </div>
        </div>
      </div>
    </div>

    <!-- Registration table -->
    <div class="card" style="margin-top:1.5rem;">
      <div class="row" style="justify-content: space-between;">
        <h2 style="margin-bottom:0;">Current registrations</h2>
        <button id="resetBtn" class="secondary">Reset all (teacher only)</button>
      </div>

      <table>
        <thead>
          <tr>
            <th style="width:70px;">Group</th>
            <th style="width:220px;">Main topic</th>
            <th>Specific subtopic</th>
          </tr>
        </thead>
        <tbody id="assignmentsBody">
        </tbody>
      </table>
    </div>
  </div>

  <!-- JavaScript -->
  <script>
    /* (JavaScript identical to previous version — omitted for brevity,
       but in your final copy please include the full JS exactly as before.) */
  </script>
</body>
</html>

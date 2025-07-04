<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Study Website</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f7fa;
      color: #333;
    }
    header {
      background-color: #4f46e5;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    main {
      padding: 2rem;
    }
    h2 {
      margin-bottom: 1rem;
    }
    .subjects {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem;
    }
    .card {
      background: white;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      cursor: pointer;
      transition: transform 0.2s ease;
    }
    .card:hover {
      transform: translateY(-5px);
    }
    .notes {
      margin-top: 2rem;
    }
    .back-btn {
      background: #4f46e5;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <header>
    <h1>My Study Website</h1>
    <p>Choose a subject to start learning</p>
  </header>
  <main>
    <section class="subjects" id="subjectList">
      <div class="card" onclick="showNotes('math')">📘 Mathematics</div>
      <div class="card" onclick="showNotes('science')">🔬 Science</div>
      <div class="card" onclick="showNotes('history')">📜 History</div>
    </section><section class="notes" id="notesSection" style="display: none">
  <button class="back-btn" onclick="goBack()">← Back</button>
  <h2 id="notesTitle"></h2>
  <ul id="notesContent"></ul>
</section>

  </main>  <script>
    const notesData = {
      math: [
        'Algebra basics',
        'Geometry formulas',
        'Trigonometry overview'
      ],
      science: [
        'Physics laws',
        'Chemistry periodic table',
        'Biology cells & systems'
      ],
      history: [
        'Ancient civilizations',
        'World War timelines',
        'Freedom movement of India'
      ]
    };

    function showNotes(subject) {
      document.getElementById('subjectList').style.display = 'none';
      document.getElementById('notesSection').style.display = 'block';
      document.getElementById('notesTitle').textContent = subject.charAt(0).toUpperCase() + subject.slice(1);
      const notesList = document.getElementById('notesContent');
      notesList.innerHTML = '';
      notesData[subject].forEach(note => {
        const li = document.createElement('li');
        li.textContent = note;
        notesList.appendChild(li);
      });
    }

    function goBack() {
      document.getElementById('subjectList').style.display = 'grid';
      document.getElementById('notesSection').style.display = 'none';
    }
  </script></body>
</html>

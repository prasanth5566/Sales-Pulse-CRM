<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SalesPulse CRM</title>
    <style>
        /* Base Styles */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: #f9fafb;
            color: #333;
            transition: background-color 0.3s ease;
        }

        header {
            background: linear-gradient(135deg, #0078d4, #005a9e);
            color: white;
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }

        header h1 {
            font-size: 1.8rem;
            margin: 0;
        }

        nav {
            display: flex;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 1.5rem;
            font-weight: bold;
            font-size: 1.1rem;
        }

        nav a:hover {
            text-decoration: underline;
        }

        .container {
            padding: 2rem;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .card {
            background: white;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }

        .card h3 {
            margin-top: 0;
        }

        .card p {
            font-size: 1rem;
            line-height: 1.5;
        }

        .button {
            background: #0078d4;
            color: white;
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .button:hover {
            background: #005a9e;
        }

        .button:disabled {
            background: #c3d4e2;
            cursor: not-allowed;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .quick-actions {
            display: flex;
            justify-content: space-between;
            margin-bottom: 2rem;
        }

        .quick-actions button {
            background: #4caf50;
            color: white;
            border-radius: 4px;
            padding: 0.75rem 1.5rem;
        }

        .quick-actions button:hover {
            background: #388e3c;
        }

        .progress-bar {
            height: 8px;
            background-color: #e0e0e0;
            border-radius: 4px;
            margin-top: 1rem;
        }

        .progress-bar span {
            display: block;
            height: 100%;
            background-color: #0078d4;
            width: 0;
            transition: width 0.5s ease;
        }

        .search-bar {
            margin-bottom: 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .search-bar input {
            padding: 0.75rem;
            width: 100%;
            max-width: 400px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }

        /* Pie Chart container */
        .chart-container {
            width: 100%;
            height: 300px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .chart {
            width: 70%;
            height: 70%;
            background: linear-gradient(45deg, #0078d4 50%, #005a9e 50%);
            border-radius: 50%;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .chart .percentage {
            font-size: 2rem;
            color: white;
        }

    </style>
</head>
<body>
    <header>
        <h1>SalesPulse CRM</h1>
        <nav>
            <a href="#" id="lead-listing-tab" onclick="showTab('lead-listing')">Leads</a>
            <a href="#" id="lead-details-tab" onclick="showTab('lead-details')">Lead Details</a>
            <a href="#" id="lead-management-tab" onclick="showTab('lead-management')">Management</a>
            <a href="#" id="dashboard-tab" onclick="showTab('dashboard')">Dashboard</a>
        </nav>
    </header>

    <main class="container">
        <!-- Screen 1: Lead Listing -->
        <section id="lead-listing" class="tab-content active">
            <h2>Lead Listing</h2>
            <div class="search-bar">
                <input type="text" id="search" placeholder="Search Leads...">
            </div>
            <div class="grid">
                <div class="card">
                    <h3>John Doe</h3>
                    <p>Email: john.doe@example.com</p>
                    <p>Status: New</p>
                    <button class="button">View Details</button>
                </div>
                <div class="card">
                    <h3>Jane Smith</h3>
                    <p>Email: jane.smith@example.com</p>
                    <p>Status: Contacted</p>
                    <button class="button">View Details</button>
                </div>
                <div class="card">
                    <h3>Robert Brown</h3>
                    <p>Email: robert.brown@example.com</p>
                    <p>Status: Not Interested</p>
                    <button class="button">View Details</button>
                </div>
            </div>
        </section>

        <!-- Screen 2: Lead Details -->
        <section id="lead-details" class="tab-content">
            <h2>Lead Details</h2>
            <div class="card">
                <h3>John Doe</h3>
                <p>Email: john.doe@example.com</p>
                <p>Phone: (123) 456-7890</p>
                <p>Status: 
                    <select>
                        <option>New</option>
                        <option>Contacted</option>
                        <option>Not Interested</option>
                    </select>
                </p>
                <h4>Notes</h4>
                <textarea rows="4" placeholder="Add a note..."></textarea>
                <br><br>
                <button class="button">Save</button>
            </div>
        </section>

        <!-- Screen 3: Lead Management -->
        <section id="lead-management" class="tab-content">
            <h2>Lead Management</h2>
            <div class="grid">
                <div class="card">
                    <h3>Assign Leads</h3>
                    <p>Drag and drop leads into team buckets or assign in bulk.</p>
                    <button class="button">Upload Leads</button>
                </div>
                <div class="card">
                    <h3>Automation Rules</h3>
                    <p>Create rules to auto-assign leads based on source or criteria.</p>
                    <button class="button">Create Rule</button>
                </div>
            </div>
        </section>

        <!-- Screen 4: Dashboard (Business Manager) -->
        <section id="dashboard" class="tab-content">
            <h2>Dashboard</h2>
            <div class="grid">
                <!-- Pie Chart Visualization -->
                <div class="card chart-container">
                    <div class="chart">
                        <span class="percentage">60%</span>
                    </div>
                </div>

                <div class="card">
                    <h3>Key Metrics</h3>
                    <p>Total Leads: 150</p>
                    <p>Contacted: 50</p>
                    <p>Converted: 20</p>
                    <div class="progress-bar">
                        <span style="width: 60%;"></span>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <script>
        function showTab(tabId) {
            const tabs = document.querySelectorAll('.tab-content');
            tabs.forEach(tab => {
                tab.classList.remove('active');
            });

            const activeTab = document.getElementById(tabId);
            activeTab.classList.add('active');

            const navLinks = document.querySelectorAll('nav a');
            navLinks.forEach(link => {
                link.classList.remove('active');
            });
            document.getElementById(tabId + '-tab').classList.add('active');
        }

        document.getElementById('search').addEventListener('input', function(event) {
            const query = event.target.value.toLowerCase();
            const cards = document.querySelectorAll('.card');
            cards.forEach(card => {
                const name = card.querySelector('h3').textContent.toLowerCase();
                if (name.includes(query)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        });
    </script>
</body>
</html>

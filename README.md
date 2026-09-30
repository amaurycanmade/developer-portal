<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AMAURYCAN MADE | Universal Sovereign Gateway & ROD-Portal Hub</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;700;800&family=Open+Sans:wght@400;600&family=Roboto+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-dark: #0f172a;
            --bg-card: #1e293b;
            --bg-card-hover: #334155;
            --accent-sky: #0284c7;
            --accent-sky-light: #38bdf8;
            --accent-emerald: #10b981;
            --accent-amber: #f59e0b;
            --accent-red: #dc2626;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --border-color: #334155;
            --font-head: 'Montserrat', sans-serif;
            --font-body: 'Open Sans', sans-serif;
            --font-code: 'Roboto Mono', ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { background-color: var(--bg-dark); color: var(--text-primary); font-family: var(--font-body); line-height: 1.6; }

        /* Force Monospace Typography Enforcer */
        code, pre, .badge-tag, .rank-badge, .tax-receipt-box, .status-pill, .tile-tag, .card-tag {
            font-family: var(--font-code) !important;
            letter-spacing: -0.3px;
        }

        /* ROD Governance Top Seal Banner */
        .top-seal-bar { background: #020617; border-bottom: 1px solid var(--border-color); padding: 8px 24px; font-size: 11px; font-family: var(--font-code); color: var(--text-secondary); display: flex; justify-content: space-between; align-items: center; }
        .top-seal-bar .seal-title { color: var(--accent-sky-light); font-weight: 700; }
        .top-seal-bar .status-pill { background: #10b98122; color: var(--accent-emerald); border: 1px solid var(--accent-emerald); padding: 2px 8px; border-radius: 12px; }

        /* Header Navigation */
        header { position: sticky; top: 0; z-index: 100; background: rgba(15, 23, 42, 0.95); backdrop-filter: blur(12px); border-bottom: 1px solid var(--border-color); padding: 16px 24px; display: flex; justify-content: space-between; align-items: center; }
        .logo { font-family: var(--font-head); font-weight: 800; font-size: 18px; color: var(--text-primary); text-decoration: none; letter-spacing: -0.5px; display: flex; align-items: center; gap: 8px; }
        .badge-tag { font-family: var(--font-code); font-size: 11px; background: #0284c722; color: var(--accent-sky-light); border: 1px solid var(--accent-sky); padding: 2px 8px; border-radius: 4px; }
        nav { display: flex; gap: 16px; align-items: center; }
        nav a { color: var(--text-secondary); text-decoration: none; font-size: 13px; font-weight: 600; transition: color 0.2s; }
        nav a:hover, nav a.active { color: var(--accent-sky-light); }
        .btn-cta { background-color: var(--accent-sky); color: #fff; padding: 8px 16px; border-radius: 6px; font-weight: 600; font-size: 13px; text-decoration: none; transition: background 0.2s; border: none; cursor: pointer; }
        .btn-cta:hover { background-color: #0369a1; }

        /* Main Shell & Container */
        .container { max-width: 1200px; margin: 0 auto; padding: 32px 24px; }
        section { margin-bottom: 56px; scroll-margin-top: 120px; }

        /* ROD Portal Hero & Universal Search */
        .rod-hero { background: linear-gradient(180deg, #1e293b 0%, #0f172a 100%); border: 1px solid var(--border-color); border-radius: 16px; padding: 48px 32px; text-align: center; margin-bottom: 40px; box-shadow: 0 20px 25px -5px rgba(0,0,0,0.3); }
        .rod-hero h1 { font-family: var(--font-head); font-size: 36px; font-weight: 800; line-height: 1.2; margin-bottom: 12px; background: linear-gradient(90deg, #fff, #94a3b8); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .rod-hero p { font-size: 16px; color: var(--text-secondary); max-width: 760px; margin: 0 auto 28px; }

        /* Universal Search Bar */
        .search-box-container { max-width: 720px; margin: 0 auto 20px; position: relative; }
        .search-input { width: 100%; background: #0b1329; border: 2px solid var(--accent-sky); color: #fff; padding: 16px 20px 16px 48px; border-radius: 50px; font-size: 15px; font-family: var(--font-body); box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.4); transition: border-color 0.2s; }
        .search-input:focus { outline: none; border-color: var(--accent-emerald); }
        .search-icon { position: absolute; left: 18px; top: 50%; transform: translateY(-50%); color: var(--accent-sky-light); font-size: 18px; }
        .quick-verify-btn { position: absolute; right: 8px; top: 50%; transform: translateY(-50%); background: var(--accent-emerald); color: #000; font-weight: 700; padding: 10px 20px; border-radius: 40px; border: none; cursor: pointer; font-size: 13px; }
        .quick-verify-btn:hover { background: #34d399; }

        /* Action Quick Tiles (ROD Grid Style) */
        .tile-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; margin-bottom: 40px; }
        .tile { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: 12px; padding: 24px; transition: transform 0.2s, border-color 0.2s, background 0.2s; text-decoration: none; color: inherit; display: block; }
        .tile:hover { transform: translateY(-4px); border-color: var(--accent-sky); background: var(--bg-card-hover); }
        .tile-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; }
        .tile-icon { font-size: 24px; }
        .tile-tag { font-family: var(--font-code); font-size: 10px; background: #334155; color: var(--accent-sky-light); padding: 2px 6px; border-radius: 4px; }
        .tile h3 { font-family: var(--font-head); font-size: 18px; font-weight: 700; margin-bottom: 8px; }
        .tile p { font-size: 13px; color: var(--text-secondary); line-height: 1.5; }

        /* Bento Cards & Resource Pointers */
        .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 24px; }
        .card { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: 12px; padding: 28px; transition: transform 0.2s, border-color 0.2s; }
        .card:hover { transform: translateY(-4px); border-color: var(--accent-sky); }
        .card-tag { font-family: var(--font-code); font-size: 12px; color: var(--accent-emerald); margin-bottom: 12px; display: block; }
        .card h3 { font-family: var(--font-head); font-size: 20px; margin-bottom: 12px; }
        .card p { color: var(--text-secondary); font-size: 14px; margin-bottom: 20px; }
        .card-link { color: var(--accent-sky-light); text-decoration: none; font-weight: 600; font-size: 14px; display: inline-flex; align-items: center; gap: 6px; }

        /* Leaderboard & Verification Modal */
        .table-wrapper { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: 12px; overflow: hidden; }
        table { width: 100%; border-collapse: collapse; text-align: left; font-size: 14px; }
        th { background: #0f172a; padding: 16px 20px; font-family: var(--font-code); font-size: 12px; color: var(--text-secondary); border-bottom: 1px solid var(--border-color); }
        td { padding: 16px 20px; border-bottom: 1px solid var(--border-color); }
        tr:last-child td { border-bottom: none; }
        .rank-badge { font-family: var(--font-code); font-weight: 700; color: var(--accent-amber); }
        .progress-bar-bg { background: #334155; height: 12px; border-radius: 6px; overflow: hidden; margin-top: 8px; }
        .progress-bar-fill { background: linear-gradient(90deg, var(--accent-sky), var(--accent-emerald)); height: 100%; width: 85%; }

        /* Forms & Interactive Tax Engine */
        .form-card { background: var(--bg-card); border: 1px solid var(--border-color); border-radius: 12px; padding: 32px; max-width: 640px; margin: 0 auto; }
        .form-group { margin-bottom: 20px; }
        .form-group label { display: block; font-size: 13px; font-weight: 600; margin-bottom: 8px; color: var(--text-secondary); }
        .form-control { width: 100%; background: #0f172a; border: 1px solid var(--border-color); color: #fff; padding: 12px 16px; border-radius: 6px; font-family: var(--font-body); font-size: 14px; }
        .form-control:focus { outline: none; border-color: var(--accent-sky); }
        .tax-receipt-box { background: #090e1a; border: 1px dashed var(--accent-sky); border-radius: 8px; padding: 16px; margin-top: 20px; font-family: var(--font-code); font-size: 13px; }
        .receipt-row { display: flex; justify-content: space-between; margin-bottom: 6px; }
        .receipt-total { border-top: 1px solid var(--border-color); padding-top: 8px; font-weight: 700; color: var(--accent-emerald); font-size: 15px; }

        /* Modal Popup System */
        .modal-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.85); backdrop-filter: blur(8px); z-index: 200; display: none; justify-content: center; align-items: center; padding: 20px; }
        .modal-card { background: var(--bg-card); border: 1px solid var(--accent-sky); border-radius: 16px; max-width: 560px; width: 100%; padding: 32px; position: relative; box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5); }
        .modal-close { position: absolute; right: 20px; top: 20px; background: none; border: none; color: var(--text-secondary); font-size: 20px; cursor: pointer; }
        .modal-close:hover { color: #fff; }

        /* Footer */
        footer { background: #0b1329; border-top: 1px solid var(--border-color); padding: 40px 24px; text-align: center; font-size: 13px; color: var(--text-secondary); }
        footer code { font-family: var(--font-code); color: var(--accent-emerald); }
    </style>
</head>
<body>

    <!-- ROD Governance Top Seal Banner -->
    <div class="top-seal-bar">
        <div>
            <span class="seal-title">AMAURYCAN ENTERPRISE GATEWAY</span> | ARCHITECT: <code>Terrell M. Wilson (L0 System Architect)</code>
        </div>
        <div>
            DOMAIN: <span class="seal-title">amaurycan.com</span> | <span class="status-pill">STATE MADE</span>
        </div>
    </div>

    <!-- Header & Navigation Bar -->
    <header data-dots="00.00.00.00.00.00.00.00.00.00">
        <a href="#home" class="logo">
            AMAURYCAN PORTAL <span class="badge-tag">[ARCH]₀ ROD-SPEC</span>
        </a>
        <nav>
            <a href="#home">Home</a>
            <a href="#apps">Resource Tiles</a>
            <a href="#b2b">B2B IT Services</a>
            <a href="#verify" onclick="openVerifyModal('INV-MARVIN-2026-0101')">Verify Record</a>
            <a href="#leaderboard">Leaderboard</a>
            <a href="#donate">4KT Trust</a>
            <a href="#onboard" class="btn-cta">Intake Portal</a>
        </nav>
    </header>

    <main class="container">

        <!-- ROD-Portal Universal Search & Hero Banner -->
        <section id="home" class="rod-hero" data-dots="00.10.00.00.00.00.00.00.00.00">
            <h1>UNIVERSAL SOVEREIGN RESOURCE GATEWAY</h1>
            <p>Access official B2B IT infrastructure tools, record verification ledgers, event portals, and gamified AI-role task execution.</p>

            <!-- Live Universal Search Bar -->
            <div class="search-box-container">
                <span class="search-icon">&#128099;</span>
                <input type="text" id="portalSearch" class="search-input" placeholder="Search B2B invoices, certificates, SOWs, or services (e.g. 'Marvin', 'PMHNP', 'TAJC')..." onkeyup="filterPortalCards()">
                <button class="quick-verify-btn" onclick="openVerifyModal(document.getElementById('portalSearch').value || 'INV-B2B-2026-TECP15')">Verify Record</button>
            </div>
            <div style="font-size:12px; color:var(--text-secondary);">
                Quick Search Tags: <code style="color:var(--accent-sky-light); cursor:pointer;" onclick="setSearch('Marvin')">#Marvin-IT</code> | <code style="color:var(--accent-sky-light); cursor:pointer;" onclick="setSearch('PMHNP')">#PMHNP-Site-License</code> | <code style="color:var(--accent-sky-light); cursor:pointer;" onclick="setSearch('TAJC')">#TAJC-2026</code> | <code style="color:var(--accent-sky-light); cursor:pointer;" onclick="setSearch('INV')">#B2B-Invoices</code>
            </div>
        </section>

        <!-- Quick Access Action Tiles (ROD Grid Style) -->
        <section id="tiles-overview">
            <h2 style="font-family:var(--font-head); font-size:20px; margin-bottom:20px; color:var(--text-primary);">Core Portal Services & Access Nodes</h2>
            <div class="tile-grid">
                <a href="#b2b" class="tile search-item">
                    <div class="tile-header">
                        <span class="tile-icon">&#128187;</span>
                        <span class="tile-tag">B2B_INV</span>
                    </div>
                    <h3>Marvin B2B IT & Painting</h3>
                    <p>Dual-trade commercial IT rack installation, patch panels, & drywall painting SOWs.</p>
                </a>
                <a href="javascript:void(0)" onclick="openVerifyModal('DDACDF.00.00.01.00')" class="tile search-item">
                    <div class="tile-header">
                        <span class="tile-icon">&#127973;</span>
                        <span class="tile-tag">B2B_PMHNP</span>
                    </div>
                    <h3>PMHNP Site License</h3>
                    <p>Clinical psychiatric facility site licenses, staff credentialing guides, & BAA shields.</p>
                </a>
                <a href="#tajc" class="tile search-item">
                    <div class="tile-header">
                        <span class="tile-icon">&#127942;</span>
                        <span class="tile-tag">TAJC-2026</span>
                    </div>
                    <h3>TAJC Juneteenth Portal</h3>
                    <p>6 registration pathways, vendor intake, sponsor tiers, & King & Queen Basketball.</p>
                </a>
                <a href="#egghunt" class="tile search-item">
                    <div class="tile-header">
                        <span class="tile-icon">&#129370;</span>
                        <span class="tile-tag">AMBG-SHIELD</span>
                    </div>
                    <h3>Southeast Egg Hunt</h3>
                    <p>Community sponsorship portal with automated paper shield agreements & 7% trust pledge.</p>
                </a>
            </div>
        </section>

        <!-- Resource Pointers & Portals Grid -->
        <section id="apps" data-dots="00.10.01.00.00.00.00.00.00.00">
            <h2 style="font-family:var(--font-head); font-size:22px; margin-bottom:24px;">Resource Pointers & Application Suites</h2>
            <div class="grid-3">
                <div class="card search-item">
                    <span class="card-tag">DP0 / DDBPRT</span>
                    <h3>Amaurycan B2B IT Portal</h3>
                    <p>Sovereign IT helpdesk, PATANA v.1 002 SaaS deployments, and UABAG business directory access.</p>
                    <a href="#b2b" class="card-link">Launch B2B Portal &rarr;</a>
                </div>
                <div class="card search-item">
                    <span class="card-tag">DP1 / DDORGN</span>
                    <h3>TAJC Juneteenth 2026</h3>
                    <p>TN Juneteenth Celebration portal featuring vendor intake, sponsor tiers, and youth athletic challenges.</p>
                    <a href="#onboard" class="card-link" onclick="setFormPackage('tajc_vendor')">Register Vendor &rarr;</a>
                </div>
                <div class="card search-item">
                    <span class="card-tag">DP4 / DDASSN</span>
                    <h3>Southeast Egg Hunt 2026</h3>
                    <p>Community sponsorship portal with automated AMBG legal agreements and 7% youth IT server pledge.</p>
                    <a href="#onboard" class="card-link" onclick="setFormPackage('egghunt_sponsor')">Sponsor Event &rarr;</a>
                </div>
            </div>
        </section>

        <!-- B2B IT Solutions & Packages -->
        <section id="b2b" data-dots="00.10.02.00.00.00.00.00.00.00">
            <h2 style="font-family:var(--font-head); font-size:22px; margin-bottom:24px;">B2B Commercial Packages & Service Rates</h2>
            <div class="grid-3">
                <div class="card search-item">
                    <span class="card-tag">$75.00 / STARTER</span>
                    <h3>Initial Audit & Onboarding</h3>
                    <p>120-point technical audit, workspace hygiene cleanup, and basic credential vault configuration.</p>
                    <button class="btn-cta" onclick="selectAndScrollPackage('b2b_starter')">Select Starter Package</button>
                </div>
                <div class="card search-item" style="border-color:var(--accent-sky);">
                    <span class="card-tag" style="color:var(--accent-sky-light);">$750.00 / STANDARD</span>
                    <h3>Turnkey SPA & CNAME Setup</h3>
                    <p>Complete single page application deployment, custom domain binding (`amaurycan.com`), & PWA manifest.</p>
                    <button class="btn-cta" onclick="selectAndScrollPackage('b2b_standard')">Select Standard Package</button>
                </div>
                <div class="card search-item">
                    <span class="card-tag" style="color:var(--accent-amber);">$1,500.00 / ENTERPRISE</span>
                    <h3>Full Dual-Trade Architecture</h3>
                    <p>15-page strategy manual, server rack mounting, Cat6a drops, and 20% `MADE3654KIDS.IT` server trust allocation.</p>
                    <button class="btn-cta" onclick="selectAndScrollPackage('b2b_enterprise')">Select Enterprise Package</button>
                </div>
            </div>
        </section>

        <!-- Leaderboard & Gamified AI-Role Execution (Ankergames Style) -->
        <section id="leaderboard" data-dots="00.10.03.00.00.00.00.00.00.00">
            <h2 style="font-family:var(--font-head); font-size:22px; margin-bottom:24px;">AI Subagent & Gladiator Task Execution Board</h2>
            <div class="table-wrapper">
                <table>
                    <thead>
                        <tr>
                            <th>RANK</th>
                            <th>SUBAGENT / ROLE ID</th>
                            <th>GOVERNANCE TIER</th>
                            <th>PUDL UNITS SPAWNED</th>
                            <th>AST AUDIT SCORE</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="rank-badge">#01</td>
                            <td><strong>L0 System Architect</strong> (ARCHOMNI00)</td>
                            <td><code>[ARCH]₀ / L0</code></td>
                            <td>1,420 PUD</td>
                            <td><span style="color:var(--accent-emerald); font-weight:700;">100 / 100</span></td>
                        </tr>
                        <tr>
                            <td class="rank-badge">#02</td>
                            <td><strong>Marvin Technical Lead</strong> (DDWFRL3)</td>
                            <td><code>[ACTN]₃ / L3</code></td>
                            <td>980 NAU</td>
                            <td><span style="color:var(--accent-emerald); font-weight:700;">98 / 100</span></td>
                        </tr>
                        <tr>
                            <td class="rank-badge">#03</td>
                            <td><strong>PMHNP Master Curator</strong> (DDWFRL8)</td>
                            <td><code>[COGN]∯ / L8</code></td>
                            <td>850 SEU-Db</td>
                            <td><span style="color:var(--accent-emerald); font-weight:700;">96 / 100</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- 4KT Trust Fund & Donation Progress -->
        <section id="donate" data-dots="00.10.06.00.00.00.00.00.00.00">
            <h2 style="font-family:var(--font-head); font-size:22px; margin-bottom:12px;">MADE3654KIDS.IT Server Trust Fund</h2>
            <p style="color:var(--text-secondary); margin-bottom:24px;">100% of community donations and 20% of commercial B2B service fees fund youth technology skill centers and boxing equipment grants.</p>
            <div class="card">
                <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:8px;">
                    <span style="font-weight:700; font-family:var(--font-head);">2026 Server Capitalization Goal</span>
                    <span style="font-family:var(--font-code); color:var(--accent-emerald); font-weight:700;">$8,500 / $10,000</span>
                </div>
                <div class="progress-bar-bg">
                    <div class="progress-bar-fill"></div>
                </div>
            </div>
        </section>

        <!-- Consolidated Intake & Dynamic Tax Calculator Form -->
        <section id="onboard" data-dots="00.10.08.00.00.00.00.00.00.00">
            <h2 style="font-family:var(--font-head); font-size:22px; text-align:center; margin-bottom:24px;">Consolidated Intake & Service Order Form</h2>
            <div class="form-card">
                <form id="intakeForm" onsubmit="handleFormSubmit(event)">
                    <div class="form-group">
                        <label>Full Legal Name / Entity Name</label>
                        <input type="text" id="clientName" class="form-control" placeholder="e.g. Marvin Commercial / Practice Director" required>
                    </div>
                    <div class="form-group">
                        <label>Contact Email Address</label>
                        <input type="email" id="clientEmail" class="form-control" placeholder="e.g. billing@domain.com" required>
                    </div>
                    <div class="form-group">
                        <label>Select Target Package / Registration</label>
                        <select id="packageSelect" class="form-control" onchange="calculateTaxMath()">
                            <option value="b2b_starter" data-price="75">B2B Audit & Onboarding ($75.00)</option>
                            <option value="b2b_standard" data-price="750">B2B Standard SPA & CNAME ($750.00)</option>
                            <option value="b2b_enterprise" data-price="1500" selected>B2B Enterprise Dual-Trade Package ($1,500.00)</option>
                            <option value="tajc_vendor" data-price="300">TAJC Juneteenth Vendor Booth ($300.00)</option>
                            <option value="egghunt_sponsor" data-price="500">Southeast Egg Hunt Gold Sponsor ($500.00)</option>
                        </select>
                    </div>

                    <!-- Dynamic TN Sales Tax Receipt Calculator -->
                    <div class="tax-receipt-box">
                        <div class="receipt-row">
                            <span>Package Subtotal:</span>
                            <span id="subtotalDisplay">$1,500.00</span>
                        </div>
                        <div class="receipt-row">
                            <span>TN Sales Tax (9.75%):</span>
                            <span id="taxDisplay">$146.25</span>
                        </div>
                        <div class="receipt-row">
                            <span style="color:var(--accent-amber);">20% Youth Server Pledge:</span>
                            <span id="pledgeDisplay" style="color:var(--accent-amber);">$300.00</span>
                        </div>
                        <div class="receipt-row receipt-total">
                            <span>Certified Total Due:</span>
                            <span id="totalDisplay">$1,646.25</span>
                        </div>
                    </div>

                    <button type="submit" class="btn-cta" style="width:100%; margin-top:24px; padding:14px;">Submit Order & Generate Receipt</button>
                </form>
            </div>
        </section>

    </main>

    <!-- Modal Popup Verification Engine -->
    <div id="verifyModal" class="modal-overlay">
        <div class="modal-card">
            <button class="modal-close" onclick="closeVerifyModal()">&times;</button>
            <h3 style="font-family:var(--font-head); color:var(--accent-sky-light); margin-bottom:12px;">Record Verification Certificate</h3>
            <p style="font-size:13px; color:var(--text-secondary); margin-bottom:20px;">Verification query for: <code id="modalRecordId" style="color:var(--accent-emerald);">INV-B2B-2026-TECP15</code></p>

            <div style="background:#090e1a; border:1px solid var(--border-color); padding:16px; border-radius:8px; font-family:var(--font-code); font-size:12px; margin-bottom:20px;">
                <div style="color:var(--accent-emerald); margin-bottom:8px;">&#10004; RECORD VERIFIED IN B2B.db LEDGER</div>
                <div>Status: <span style="color:#fff;">STATE MADE (Certified)</span></div>
                <div>Subnet Coordinate: <span>00.10.20.30.40.00</span></div>
                <div>Fiduciary Tax: <span>9.75% TN Sales Tax Verified</span></div>
                <div>Micro-Seal: <span>A32_815B063B</span></div>
            </div>

            <button class="btn-cta" style="width:100%;" onclick="closeVerifyModal()">Close Inspection Window</button>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 AMAURYCAN ENTERPRISE SOLUTIONS. All rights reserved.</p>
        <p style="margin-top:8px;">Governance Framework: <code>STATE MADE</code> | Subnet: <code>00.00.00.00.00.00.00.00.00.00</code></p>
    </footer>

    <!-- Client-Side JavaScript Logic -->
    <script>
        // 1. Live Universal Portal Search
        function filterPortalCards() {
            const query = document.getElementById('portalSearch').value.toLowerCase();
            const items = document.querySelectorAll('.search-item');
            items.forEach(item => {
                const text = item.textContent.toLowerCase();
                if (text.includes(query)) {
                    item.style.display = '';
                } else {
                    item.style.display = 'none';
                }
            });
        }

        function setSearch(tag) {
            document.getElementById('portalSearch').value = tag;
            filterPortalCards();
        }

        // 2. Dynamic TN Sales Tax Calculator
        function calculateTaxMath() {
            const select = document.getElementById('packageSelect');
            const price = parseFloat(select.options[select.selectedIndex].getAttribute('data-price')) || 0;
            const tax = price * 0.0975;
            const pledge = price * 0.20;
            const total = price + tax;

            document.getElementById('subtotalDisplay').textContent = '$' + price.toFixed(2);
            document.getElementById('taxDisplay').textContent = '$' + tax.toFixed(2);
            document.getElementById('pledgeDisplay').textContent = '$' + pledge.toFixed(2);
            document.getElementById('totalDisplay').textContent = '$' + total.toFixed(2);
        }

        function selectAndScrollPackage(pkgValue) {
            document.getElementById('packageSelect').value = pkgValue;
            calculateTaxMath();
            window.location.hash = '#onboard';
        }

        function setFormPackage(pkgValue) {
            document.getElementById('packageSelect').value = pkgValue;
            calculateTaxMath();
        }

        // 3. Modal Verification Window
        function openVerifyModal(recordId) {
            document.getElementById('modalRecordId').textContent = recordId;
            document.getElementById('verifyModal').style.display = 'flex';
        }

        function closeVerifyModal() {
            document.getElementById('verifyModal').style.display = 'none';
        }

        // 4. Form Submission Handler
        function handleFormSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('clientName').value;
            openVerifyModal('INV-B2B-ORDER-' + name.toUpperCase().replace(/\s+/g, '-'));
        }

        // Initialize Tax Math on Load
        calculateTaxMath();
    </script>
</body>
</html>

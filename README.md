<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Hari Krishna — Cloud / DevOps Engineer (Infra Heavy)</title>
  <style>
    /* ── Reset ──────────────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    /* ── Tokens ─────────────────────────────────────────────── */
    :root {
      --bg:         #0d1117;
      --surface:    #161b22;
      --border:     #30363d;
      --border-sub: #21262d;
      --text:       #e6edf3;
      --muted:      #8b949e;
      --blue:       #58a6ff;
      --green:      #3fb950;
      --yellow:     #d29922;
      --orange:     #f0883e;
      --purple:     #bc8cff;
      --red:        #f85149;
      --cyan:       #39d353;
      --radius:     6px;
      --font-mono:  "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace;
      --font-sans:  -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--font-sans);
      font-size: 14px;
      line-height: 1.65;
      min-height: 100vh;
      padding: 28px 16px 72px;
    }

    /* ── README wrapper ─────────────────────────────────────── */
    .readme {
      max-width: 780px;
      margin: 0 auto;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 36px 44px;
      animation: fadeUp .55s ease both;
    }
    @media (max-width: 600px) { .readme { padding: 24px 20px; } }

    /* ── Animations ─────────────────────────────────────────── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0);    }
    }
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50%       { opacity: 0; }
    }
    @keyframes pulse-glow {
      0%, 100% { box-shadow: 0 0 0 0 rgba(88,166,255,0); }
      50%       { box-shadow: 0 0 8px 2px rgba(88,166,255,.25); }
    }
    @keyframes slide-in {
      from { opacity: 0; transform: translateX(-14px); }
      to   { opacity: 1; transform: translateX(0); }
    }
    @keyframes badge-pop {
      0%   { opacity: 0; transform: scale(.82); }
      70%  { transform: scale(1.06); }
      100% { opacity: 1; transform: scale(1); }
    }

    /* staggered children */
    .stagger > * { opacity: 0; animation: fadeUp .4s ease forwards; }
    .stagger > *:nth-child(1) { animation-delay: .05s; }
    .stagger > *:nth-child(2) { animation-delay: .12s; }
    .stagger > *:nth-child(3) { animation-delay: .19s; }
    .stagger > *:nth-child(4) { animation-delay: .26s; }
    .stagger > *:nth-child(5) { animation-delay: .33s; }
    .stagger > *:nth-child(6) { animation-delay: .40s; }

    /* ── Typography ─────────────────────────────────────────── */
    h2 {
      font-size: 1.15em;
      border-bottom: 1px solid var(--border);
      padding-bottom: .35em;
      margin: 32px 0 14px;
      font-weight: 600;
      animation: slide-in .4s ease both;
    }
    h3 { font-size: 1em; margin: 20px 0 10px; font-weight: 600; color: var(--text); }
    p  { margin-bottom: 12px; color: var(--text); }
    a  { color: var(--blue); text-decoration: none; }
    a:hover { text-decoration: underline; }
    hr { border: none; border-top: 1px solid var(--border); margin: 28px 0; }

    code {
      font-family: var(--font-mono);
      font-size: .82em;
      background: #1f2937;
      border: 1px solid var(--border-sub);
      border-radius: 3px;
      padding: 2px 6px;
      color: var(--orange);
    }

    ul { padding-left: 22px; margin-bottom: 10px; }
    li { margin: 5px 0; }
    li::marker { color: var(--muted); }

    /* ── Table ──────────────────────────────────────────────── */
    table { width: 100%; border-collapse: collapse; margin: 14px 0; font-size: .88em; }
    th {
      background: var(--bg);
      border: 1px solid var(--border);
      padding: 7px 12px;
      text-align: left;
      color: var(--muted);
      font-weight: 600;
      font-size: .72em;
      text-transform: uppercase;
      letter-spacing: .05em;
    }
    td { border: 1px solid var(--border); padding: 7px 12px; vertical-align: top; }
    tr:nth-child(even) td { background: rgba(255,255,255,.02); }

    blockquote {
      border-left: 3px solid var(--border);
      padding: 4px 14px;
      color: var(--muted);
      margin: 12px 0;
      font-style: italic;
    }

    /* ── Badge pills ────────────────────────────────────────── */
    .badges { display: flex; flex-wrap: wrap; gap: 7px; margin: 10px 0; }
    .badge {
      font-family: var(--font-mono);
      font-size: .7em;
      padding: 3px 10px;
      border-radius: 20px;
      border: 1px solid;
      white-space: nowrap;
      font-weight: 600;
      animation: badge-pop .35s ease both;
      transition: transform .15s ease, box-shadow .15s ease;
      cursor: default;
    }
    .badge:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(0,0,0,.4); }

    .badge-blue   { background: rgba(88,166,255,.1);  border-color: rgba(88,166,255,.4);  color: var(--blue);   }
    .badge-green  { background: rgba(63,185,80,.1);   border-color: rgba(63,185,80,.4);   color: var(--green);  }
    .badge-orange { background: rgba(240,136,62,.1);  border-color: rgba(240,136,62,.4);  color: var(--orange); }
    .badge-purple { background: rgba(188,140,255,.1); border-color: rgba(188,140,255,.4); color: var(--purple); }
    .badge-yellow { background: rgba(210,153,34,.1);  border-color: rgba(210,153,34,.4);  color: var(--yellow); }
    .badge-red    { background: rgba(248,81,73,.1);   border-color: rgba(248,81,73,.4);   color: var(--red);    }
    .badge-cyan   { background: rgba(57,211,83,.1);   border-color: rgba(57,211,83,.4);   color: var(--cyan);   }
    .badge-muted  { background: rgba(139,148,158,.07);border-color: rgba(139,148,158,.28);color: var(--muted);  }

    /* ── HERO ───────────────────────────────────────────────── */
    .hero {
      text-align: center;
      padding: 4px 0 28px;
      animation: fadeUp .5s ease both;
    }
    .hero-name {
      font-size: 1.65em;
      font-weight: 700;
      letter-spacing: -.015em;
      margin-bottom: 8px;
    }
    .hero-title {
      font-family: var(--font-mono);
      font-size: .92em;
      color: var(--blue);
      margin-bottom: 4px;
      animation: pulse-glow 3s ease-in-out infinite;
      display: inline-block;
      padding: 2px 0;
    }
    .cursor {
      display: inline-block;
      width: 2px;
      height: .95em;
      background: var(--blue);
      margin-left: 2px;
      vertical-align: middle;
      animation: blink .85s step-end infinite;
    }
    .hero-sub {
      font-size: .85em;
      color: var(--muted);
      max-width: 500px;
      margin: 10px auto 0;
      line-height: 1.6;
    }
    .hero-badges {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 7px;
      margin-top: 18px;
    }
    .hero-badges .badge { animation-delay: calc(var(--i) * .06s); }

    /* ── Divider with label ──────────────────────────────────── */
    .divider-label {
      display: flex;
      align-items: center;
      gap: 10px;
      margin: 30px 0 18px;
      color: var(--muted);
      font-size: .72em;
      font-family: var(--font-mono);
      text-transform: uppercase;
      letter-spacing: .1em;
    }
    .divider-label::before,
    .divider-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    /* ── Cards grid ─────────────────────────────────────────── */
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin: 14px 0;
    }
    @media (max-width: 580px) { .grid-2 { grid-template-columns: 1fr; } }

    .card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 14px 16px;
      transition: border-color .2s ease, transform .2s ease;
      animation: fadeUp .4s ease both;
    }
    .card:hover {
      border-color: rgba(88,166,255,.35);
      transform: translateY(-2px);
    }
    .card-title {
      font-size: .68em;
      font-weight: 700;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: .08em;
      margin-bottom: 9px;
    }
    .card ul { padding-left: 16px; }
    .card li { font-size: .86em; margin: 3px 0; }

    /* ── Failure scenarios ──────────────────────────────────── */
    .scenario-list { margin: 12px 0; }
    .scenario {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      padding: 9px 0;
      border-bottom: 1px solid var(--border-sub);
      font-size: .87em;
      animation: slide-in .4s ease both;
    }
    .scenario:last-child { border-bottom: none; }
    .scenario-icon { flex-shrink: 0; margin-top: 1px; }
    .scenario-cause  { color: var(--red);   font-weight: 600; }
    .scenario-arrow  { color: var(--muted); margin: 0 5px; }
    .scenario-effect { color: var(--green); }

    /* ── CI/CD summary rows ─────────────────────────────────── */
    .cicd-row {
      display: flex;
      align-items: flex-start;
      gap: 14px;
      padding: 10px 14px;
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      margin-bottom: 8px;
      transition: border-color .2s ease;
      animation: fadeUp .4s ease both;
    }
    .cicd-row:hover { border-color: rgba(88,166,255,.3); }
    .cicd-icon { font-size: 1.3em; flex-shrink: 0; margin-top: 1px; }
    .cicd-name {
      font-weight: 600;
      font-size: .9em;
      margin-bottom: 3px;
    }
    .cicd-desc { font-size: .82em; color: var(--muted); line-height: 1.5; }

    /* ── Flow arrow row ─────────────────────────────────────── */
    .flow {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 6px;
      margin: 8px 0 4px;
    }
    .flow-step {
      font-family: var(--font-mono);
      font-size: .72em;
      background: #1f2937;
      border: 1px solid var(--border-sub);
      border-radius: 4px;
      padding: 3px 9px;
      color: var(--text);
    }
    .flow-arrow { color: var(--muted); font-size: .85em; }

    /* ── Target roles ───────────────────────────────────────── */
    .role-card {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 12px 16px;
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      margin-bottom: 8px;
      transition: border-color .2s ease, transform .2s ease;
      animation: fadeUp .4s ease both;
    }
    .role-card:hover {
      border-color: rgba(88,166,255,.4);
      transform: translateX(4px);
    }
    .role-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      flex-shrink: 0;
    }
    .role-dot-blue   { background: var(--blue);   box-shadow: 0 0 6px var(--blue); }
    .role-dot-green  { background: var(--green);  box-shadow: 0 0 6px var(--green); }
    .role-dot-purple { background: var(--purple); box-shadow: 0 0 6px var(--purple); }
    .role-name { font-weight: 600; font-size: .9em; }
    .role-sub  { font-size: .78em; color: var(--muted); margin-top: 2px; }

    /* ── Connect rows ───────────────────────────────────────── */
    .link-row {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 9px 0;
      border-bottom: 1px solid var(--border-sub);
      font-size: .9em;
      animation: slide-in .4s ease both;
      transition: color .15s;
    }
    .link-row:last-child { border-bottom: none; }
    .link-icon { font-size: 1.15em; }

    /* ── Scrollbar ──────────────────────────────────────────── */
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
  </style>
</head>
<body>

<div class="readme">

  <!-- ═══════════════════════ HERO ════════════════════════════ -->
  <div class="hero">
    <div class="hero-name">👋 Hari Krishna</div>
    <div class="hero-title">&gt; Cloud / DevOps Engineer (Infra Heavy)<span class="cursor"></span></div>
    <div class="hero-sub">
      I focus on how systems <strong>fail, recover, and scale</strong> — not just how they are deployed.
      Fault-tolerant AWS infrastructure, container pipelines, and real failure testing.
    </div>
    <div class="hero-badges">
      <span class="badge badge-blue"    style="--i:0">AWS</span>
      <span class="badge badge-orange"  style="--i:1">EC2 · ALB · ASG</span>
      <span class="badge badge-green"   style="--i:2">Docker · GHCR</span>
      <span class="badge badge-purple"  style="--i:3">GitHub Actions</span>
      <span class="badge badge-yellow"  style="--i:4">CloudFormation</span>
      <span class="badge badge-cyan"    style="--i:5">S3 · CloudFront</span>
      <span class="badge badge-muted"   style="--i:6">Lambda · DynamoDB</span>
    </div>
  </div>

  <hr>

  <!-- ═══════════════════════ ROLE ════════════════════════════ -->
  <h2>🎯 Role</h2>

  <table>
    <tr>
      <th>Area</th>
      <th>What I do</th>
    </tr>
    <tr>
      <td><code>Compute</code></td>
      <td>EC2 provisioning, Launch Templates, ASG lifecycle, User Data bootstrapping</td>
    </tr>
    <tr>
      <td><code>Networking</code></td>
      <td>Custom VPC, subnets, route tables, IGW, security groups</td>
    </tr>
    <tr>
      <td><code>Load Balancing</code></td>
      <td>ALB + Target Groups, HTTP health checks, traffic routing rules</td>
    </tr>
    <tr>
      <td><code>Containers</code></td>
      <td>Docker build → push to GHCR → pull on EC2 → run as service</td>
    </tr>
    <tr>
      <td><code>CI/CD</code></td>
      <td>GitHub Actions — infra deploy (CloudFormation), S3+CF frontend, EC2 container deploy</td>
    </tr>
    <tr>
      <td><code>IaC</code></td>
      <td>CloudFormation stacks for repeatable, version-controlled infra</td>
    </tr>
    <tr>
      <td><code>Monitoring</code></td>
      <td>CloudWatch logs, metrics, alarms — instance and app level</td>
    </tr>
    <tr>
      <td><code>IAM</code></td>
      <td>EC2 / Lambda roles, least-privilege policies, no hardcoded credentials</td>
    </tr>
  </table>

  <hr>

  <!-- ═════════════════ FEATURED PROJECT ══════════════════════ -->
  <h2>🏗️ Featured Project — Auto-Healing Infrastructure</h2>

  <blockquote>Single EC2 = single point of failure. This project removes that.</blockquote>

  <h3>Architecture</h3>

  <div class="grid-2 stagger">
    <div class="card">
      <div class="card-title">Network Layer</div>
      <ul>
        <li>Custom VPC</li>
        <li>Public subnets — 2 AZs</li>
        <li>Internet Gateway + Route Tables</li>
        <li>Security Groups (ALB &amp; EC2 separated)</li>
      </ul>
    </div>
    <div class="card">
      <div class="card-title">Compute Layer</div>
      <ul>
        <li>Application Load Balancer</li>
        <li>Target Group + HTTP health checks</li>
        <li>Auto Scaling Group</li>
        <li>Launch Template — EC2 running Docker app</li>
      </ul>
    </div>
    <div class="card">
      <div class="card-title">Bootstrapping</div>
      <ul>
        <li>User Data installs Docker on launch</li>
        <li>Pulls image from GHCR automatically</li>
        <li>Starts container on port 80</li>
        <li>No manual SSH required</li>
      </ul>
    </div>
    <div class="card">
      <div class="card-title">Monitoring</div>
      <ul>
        <li>CloudWatch — CPU, health metrics</li>
        <li>ALB access logs</li>
        <li>EC2 instance status checks</li>
        <li>ASG activity history</li>
      </ul>
    </div>
  </div>

  <h3>Failure Scenarios Tested</h3>

  <div class="scenario-list">
    <div class="scenario">
      <span class="scenario-icon">🔴</span>
      <span>
        <span class="scenario-cause">EC2 instance terminated manually</span>
        <span class="scenario-arrow">→</span>
        <span class="scenario-effect">ASG detected below desired count → launched replacement</span>
      </span>
    </div>
    <div class="scenario">
      <span class="scenario-icon">🔴</span>
      <span>
        <span class="scenario-cause">Docker container stopped inside instance</span>
        <span class="scenario-arrow">→</span>
        <span class="scenario-effect">Target Group health check failed → instance marked Unhealthy</span>
      </span>
    </div>
    <div class="scenario">
      <span class="scenario-icon">🔴</span>
      <span>
        <span class="scenario-cause">Instance marked Unhealthy by ALB</span>
        <span class="scenario-arrow">→</span>
        <span class="scenario-effect">ALB stopped routing traffic to it immediately</span>
      </span>
    </div>
    <div class="scenario">
      <span class="scenario-icon">🟢</span>
      <span>
        <span class="scenario-cause">ASG launched new instance via Launch Template</span>
        <span class="scenario-arrow">→</span>
        <span class="scenario-effect">User Data ran → Docker pulled GHCR image → app started → TG: Healthy</span>
      </span>
    </div>
    <div class="scenario">
      <span class="scenario-icon">🟢</span>
      <span>
        <span class="scenario-cause">Instance passed health checks</span>
        <span class="scenario-arrow">→</span>
        <span class="scenario-effect">ALB resumed routing — zero user-visible downtime</span>
      </span>
    </div>
  </div>

  <p style="margin-top:14px">
    🔗 <a href="https://github.com/Harikrishna2525/Aws-ALB-ASG-auto-healing">github.com/Harikrishna2525/Aws-ALB-ASG-auto-healing</a>
  </p>

  <hr>

  <!-- ═════════════════ CI/CD OVERVIEW ════════════════════════ -->
  <h2>🚀 CI/CD Pipelines</h2>

  <div class="cicd-row" style="animation-delay:.05s">
    <div class="cicd-icon">🏗️</div>
    <div>
      <div class="cicd-name">CloudFormation — Infra Deploy</div>
      <div class="cicd-desc">Push changes to <code>infra/</code> → GitHub Actions deploys the stack to AWS automatically.</div>
      <div class="flow">
        <span class="flow-step">push → infra/**</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">AWS credentials</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">cfn deploy</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step" style="color:var(--green)">stack updated ✓</span>
      </div>
    </div>
  </div>

  <div class="cicd-row" style="animation-delay:.12s">
    <div class="cicd-icon">🌐</div>
    <div>
      <div class="cicd-name">S3 + CloudFront — Frontend Deploy</div>
      <div class="cicd-desc">Push to <code>main</code> → build → sync to S3 → CloudFront cache invalidation.</div>
      <div class="flow">
        <span class="flow-step">push → main</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">npm build</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">s3 sync</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">CF invalidate</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step" style="color:var(--green)">live ✓</span>
      </div>
    </div>
  </div>

  <div class="cicd-row" style="animation-delay:.19s">
    <div class="cicd-icon">🐳</div>
    <div>
      <div class="cicd-name">GHCR → EC2 — Container Deploy</div>
      <div class="cicd-desc">Push to <code>main</code> → Docker image built &amp; pushed to GHCR → SSH into EC2 → pull &amp; run container.</div>
      <div class="flow">
        <span class="flow-step">push → main</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">docker build</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">push ghcr.io</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">SSH → EC2</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step">docker pull &amp; run</span>
        <span class="flow-arrow">→</span>
        <span class="flow-step" style="color:var(--green)">deployed ✓</span>
      </div>
    </div>
  </div>

  <hr>

  <!-- ═══════════════════════ STACK ════════════════════════════ -->
  <h2>☁️ Stack</h2>

  <div class="grid-2 stagger">
    <div class="card">
      <div class="card-title">Compute &amp; Networking</div>
      <div class="badges">
        <span class="badge badge-orange">EC2</span>
        <span class="badge badge-orange">ALB</span>
        <span class="badge badge-orange">ASG</span>
        <span class="badge badge-blue">VPC</span>
        <span class="badge badge-blue">Subnets</span>
        <span class="badge badge-blue">IGW</span>
        <span class="badge badge-muted">Security Groups</span>
      </div>
    </div>
    <div class="card">
      <div class="card-title">Containers &amp; OS</div>
      <div class="badges">
        <span class="badge badge-blue">Docker</span>
        <span class="badge badge-purple">GHCR</span>
        <span class="badge badge-muted">Linux (Ubuntu)</span>
        <span class="badge badge-muted">Nginx</span>
      </div>
    </div>
    <div class="card">
      <div class="card-title">Serverless &amp; Backend</div>
      <div class="badges">
        <span class="badge badge-yellow">Lambda</span>
        <span class="badge badge-yellow">API Gateway</span>
        <span class="badge badge-green">DynamoDB</span>
      </div>
    </div>
    <div class="card">
      <div class="card-title">Storage &amp; CDN</div>
      <div class="badges">
        <span class="badge badge-cyan">S3</span>
        <span class="badge badge-cyan">CloudFront</span>
      </div>
    </div>
    <div class="card">
      <div class="card-title">IaC &amp; CI/CD</div>
      <div class="badges">
        <span class="badge badge-yellow">CloudFormation</span>
        <span class="badge badge-purple">GitHub Actions</span>
        <span class="badge badge-muted">User Data</span>
      </div>
    </div>
    <div class="card">
      <div class="card-title">Monitoring &amp; Security</div>
      <div class="badges">
        <span class="badge badge-blue">CloudWatch</span>
        <span class="badge badge-red">IAM Roles</span>
        <span class="badge badge-muted">Least Privilege</span>
      </div>
    </div>
  </div>

  <hr>

  <!-- ═══════════════════ TARGET ROLES ════════════════════════ -->
  <h2>🎯 Open To</h2>

  <div class="role-card" style="animation-delay:.05s">
    <div class="role-dot role-dot-blue"></div>
    <div>
      <div class="role-name">Cloud Engineer</div>
      <div class="role-sub">L1 – L2 · AWS-native infrastructure, compute &amp; networking focus</div>
    </div>
  </div>

  <div class="role-card" style="animation-delay:.12s">
    <div class="role-dot role-dot-green"></div>
    <div>
      <div class="role-name">DevOps Engineer — Infra Heavy</div>
      <div class="role-sub">CI/CD pipelines, container deployments, IaC, system reliability</div>
    </div>
  </div>

  <div class="role-card" style="animation-delay:.19s">
    <div class="role-dot role-dot-purple"></div>
    <div>
      <div class="role-name">Junior Platform Engineer</div>
      <div class="role-sub">Internal infra tooling, EC2 + serverless hybrid stacks, product startups</div>
    </div>
  </div>

  <hr>

  <!-- ═══════════════════════ CONNECT ══════════════════════════ -->
  <h2>📫 Connect</h2>

  <div class="link-row">
    <span class="link-icon">🌐</span>
    <span>Portfolio — <a href="https://harikrish-portfolio25.web.app">harikrish-portfolio25.web.app</a></span>
  </div>
  <div class="link-row">
    <span class="link-icon">💼</span>
    <span>LinkedIn — <a href="https://linkedin.com/in/hari-krish-13300b27a">linkedin.com/in/hari-krish-13300b27a</a></span>
  </div>
  <div class="link-row">
    <span class="link-icon">🐙</span>
    <span>GitHub — <a href="https://github.com/Harikrishna2525">github.com/Harikrishna2525</a></span>
  </div>

</div><!-- /readme -->

</body>
</html>

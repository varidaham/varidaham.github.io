# varidaham.github.io
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TIMMY — Roblox Game Tester & Discord Moderator</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@500;700&family=Space+Grotesk:wght@600;700;800&display=swap" rel="stylesheet" />

  <style>
    :root {
      --bg-primary: #050806;
      --bg-secondary: #0a0f0c;
      --bg-card: #0d1410;
      --bg-card-hover: #111c16;
      --neon: #39ff14;
      --neon-bright: #6bff4d;
      --neon-dim: rgba(57, 255, 20, 0.14);
      --neon-border: rgba(57, 255, 20, 0.25);
      --neon-border-strong: rgba(57, 255, 20, 0.6);
      --text-main: #f3faf4;
      --text-muted: #93a898;
      --text-dim: #5d7262;
      --border-subtle: rgba(255, 255, 255, 0.08);
      --radius-lg: 20px;
      --radius-md: 14px;
      --radius-sm: 10px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      background-color: var(--bg-primary);
      color: var(--text-main);
      font-family: 'Inter', system-ui, -apple-system, sans-serif;
      -webkit-font-smoothing: antialiased;
    }

    body {
      min-height: 100vh;
      overflow-x: hidden;
      background:
        radial-gradient(circle at 18% 8%, rgba(57, 255, 20, 0.12), transparent 36%),
        radial-gradient(circle at 85% 28%, rgba(57, 255, 20, 0.07), transparent 34%),
        radial-gradient(circle at 50% 92%, rgba(57, 255, 20, 0.09), transparent 40%),
        var(--bg-primary);
    }

    /* Subtle cyber grid background */
    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(57, 255, 20, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(57, 255, 20, 0.03) 1px, transparent 1px);
      background-size: 56px 56px;
      mask-image: radial-gradient(ellipse at center, black 35%, transparent 85%);
      pointer-events: none;
      z-index: -1;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: 100%;
      max-width: 1180px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* Navbar */
    .navbar {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      background: rgba(5, 8, 6, 0.78);
      border-bottom: 1px solid var(--border-subtle);
    }

    .nav-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 76px;
      gap: 20px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .brand-logo {
      height: 46px;
      width: auto;
      object-fit: contain;
      filter: drop-shadow(0 0 12px rgba(57, 255, 20, 0.35));
      transition: transform 0.25s ease;
    }

    .brand:hover .brand-logo {
      transform: scale(1.04);
    }

    .brand-fallback {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 800;
      font-size: 1.35rem;
      letter-spacing: -0.03em;
      color: var(--neon);
      text-shadow: 0 0 18px rgba(57, 255, 20, 0.45);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
    }

    .nav-links a {
      font-size: 0.92rem;
      font-weight: 500;
      color: var(--text-muted);
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--neon);
    }

    .nav-cta {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 10px 18px;
      border-radius: 999px;
      background: var(--neon);
      color: #030604;
      font-weight: 700;
      font-size: 0.88rem;
      box-shadow: 0 0 22px rgba(57, 255, 20, 0.3);
      transition: transform 0.2s ease, box-shadow 0.2s ease, background 0.2s ease;
    }

    .nav-cta:hover {
      background: var(--neon-bright);
      transform: translateY(-1px);
      box-shadow: 0 0 30px rgba(57, 255, 20, 0.55);
    }

    /* Hero Section */
    .hero {
      padding: 78px 0 64px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 48px;
      align-items: center;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 7px 14px;
      border-radius: 999px;
      background: var(--neon-dim);
      border: 1px solid var(--neon-border);
      color: var(--neon);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      font-weight: 700;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      margin-bottom: 22px;
    }

    .pulse-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--neon);
      box-shadow: 0 0 10px var(--neon);
      animation: pulse 1.8s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.45; transform: scale(1.3); }
    }

    .hero h1 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(2.5rem, 5vw, 4.1rem);
      line-height: 1.04;
      letter-spacing: -0.035em;
      font-weight: 800;
      margin-bottom: 22px;
    }

    .hero h1 .accent {
      color: var(--neon);
      text-shadow: 0 0 32px rgba(57, 255, 20, 0.35);
    }

    .hero-desc {
      font-size: 1.08rem;
      line-height: 1.65;
      color: var(--text-muted);
      max-width: 580px;
      margin-bottom: 32px;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-bottom: 38px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 13px 24px;
      border-radius: 12px;
      font-weight: 700;
      font-size: 0.95rem;
      cursor: pointer;
      border: 1px solid transparent;
      transition: all 0.22s ease;
    }

    .btn-primary {
      background: var(--neon);
      color: #040705;
      box-shadow: 0 0 26px rgba(57, 255, 20, 0.28);
    }

    .btn-primary:hover {
      background: var(--neon-bright);
      transform: translateY(-2px);
      box-shadow: 0 0 36px rgba(57, 255, 20, 0.5);
    }

    .btn-secondary {
      background: rgba(255, 255, 255, 0.03);
      color: var(--text-main);
      border-color: var(--neon-border);
    }

    .btn-secondary:hover {
      background: var(--neon-dim);
      border-color: var(--neon);
      color: var(--neon);
      transform: translateY(-2px);
    }

    .hero-metrics {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 16px;
      padding-top: 26px;
      border-top: 1px solid var(--border-subtle);
    }

    .metric-item {
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .metric-val {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.55rem;
      font-weight: 800;
      color: var(--text-main);
    }

    .metric-val span {
      color: var(--neon);
    }

    .metric-label {
      font-size: 0.8rem;
      color: var(--text-muted);
      font-family: 'JetBrains Mono', monospace;
    }

    /* Hero Right Logo Card */
    .hero-showcase {
      position: relative;
      border-radius: 26px;
      background: linear-gradient(145deg, #0d1610, #060907);
      border: 1px solid var(--neon-border);
      padding: 36px 28px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      box-shadow:
        0 24px 60px rgba(0, 0, 0, 0.65),
        inset 0 0 40px rgba(57, 255, 20, 0.06);
      overflow: hidden;
    }

    .hero-showcase::before {
      content: "";
      position: absolute;
      width: 260px;
      height: 260px;
      background: radial-gradient(circle, rgba(57, 255, 20, 0.24), transparent 70%);
      top: -60px;
      right: -60px;
      pointer-events: none;
    }

    .hero-logo-img {
      width: 100%;
      max-width: 340px;
      height: auto;
      object-fit: contain;
      filter: drop-shadow(0 14px 28px rgba(57, 255, 20, 0.28));
      margin-bottom: 22px;
      animation: float 5s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-7px); }
    }

    .showcase-badges {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
    }

    .tag-pill {
      padding: 7px 13px;
      border-radius: 999px;
      background: rgba(57, 255, 20, 0.08);
      border: 1px solid var(--neon-border);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.76rem;
      color: var(--neon);
    }

    /* Section Headers */
    section {
      padding: 72px 0;
    }

    .section-header {
      display: flex;
      flex-wrap: wrap;
      align-items: flex-end;
      justify-content: space-between;
      gap: 20px;
      margin-bottom: 36px;
    }

    .section-kicker {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.8rem;
      font-weight: 700;
      color: var(--neon);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 10px;
    }

    .section-title {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(1.85rem, 3.2vw, 2.6rem);
      font-weight: 800;
      letter-spacing: -0.03em;
      line-height: 1.1;
    }

    .section-sub {
      color: var(--text-muted);
      font-size: 0.98rem;
      margin-top: 8px;
      max-width: 580px;
    }

    /* Live sync bar */
    .live-sync-pill {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 9px 14px;
      border-radius: 999px;
      background: var(--bg-card);
      border: 1px solid var(--neon-border);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.76rem;
      color: var(--text-muted);
    }

    .refresh-btn {
      background: var(--neon-dim);
      color: var(--neon);
      border: 1px solid var(--neon-border);
      border-radius: 999px;
      padding: 4px 10px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      font-weight: 700;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    .refresh-btn:hover {
      background: var(--neon);
      color: #030604;
    }

    /* Games Grid */
    .games-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 24px;
    }

    .game-card {
      background: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-lg);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
    }

    .game-card:hover {
      transform: translateY(-5px);
      border-color: var(--neon-border-strong);
      box-shadow: 0 20px 48px rgba(0, 0, 0, 0.55), 0 0 28px rgba(57, 255, 20, 0.12);
    }

    .game-thumb-wrap {
      position: relative;
      aspect-ratio: 16 / 9;
      background: #070b08;
      overflow: hidden;
      border-bottom: 1px solid var(--border-subtle);
    }

    .game-thumb {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.4s ease;
    }

    .game-card:hover .game-thumb {
      transform: scale(1.04);
    }

    .role-badge {
      position: absolute;
      top: 14px;
      left: 14px;
      padding: 6px 12px;
      border-radius: 999px;
      background: rgba(5, 8, 6, 0.86);
      backdrop-filter: blur(8px);
      border: 1px solid var(--neon);
      color: var(--neon);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.04em;
      text-transform: uppercase;
      box-shadow: 0 0 14px rgba(57, 255, 20, 0.25);
    }

    .live-chip {
      position: absolute;
      top: 14px;
      right: 14px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 5px 10px;
      border-radius: 999px;
      background: rgba(5, 8, 6, 0.86);
      backdrop-filter: blur(8px);
      border: 1px solid rgba(57, 255, 20, 0.4);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.7rem;
      font-weight: 700;
      color: #e9ffea;
    }

    /* Custom Banner for Wave Byte Games (no image/link) */
    .wavebyte-banner {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 20px;
      background:
        radial-gradient(circle at 50% 45%, rgba(57, 255, 20, 0.22), transparent 65%),
        linear-gradient(135deg, #07110a 0%, #030604 100%);
      position: relative;
    }

    .wavebyte-emblem {
      width: 56px;
      height: 56px;
      border-radius: 14px;
      background: rgba(57, 255, 20, 0.12);
      border: 1px solid var(--neon);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--neon);
      box-shadow: 0 0 24px rgba(57, 255, 20, 0.25);
    }

    .wavebyte-title-art {
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 800;
      font-size: 1.25rem;
      letter-spacing: 0.08em;
      color: var(--text-main);
    }

    .wavebyte-title-art span {
      color: var(--neon);
    }

    .game-body {
      padding: 22px;
      display: flex;
      flex-direction: column;
      flex: 1;
    }

    .game-title {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.35rem;
      font-weight: 700;
      margin-bottom: 8px;
      letter-spacing: -0.02em;
    }

    .game-desc {
      font-size: 0.92rem;
      line-height: 1.55;
      color: var(--text-muted);
      margin-bottom: 18px;
      flex: 1;
    }

    /* Live stats inside card */
    .stats-row {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
      margin-bottom: 18px;
    }

    .stat-box {
      background: rgba(255, 255, 255, 0.025);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-sm);
      padding: 10px 12px;
    }

    .stat-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.68rem;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      color: var(--text-dim);
      margin-bottom: 4px;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .stat-value {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--text-main);
    }

    .stat-value.neon {
      color: var(--neon);
    }

    .game-link-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      width: 100%;
      padding: 12px 16px;
      border-radius: 12px;
      background: rgba(57, 255, 20, 0.09);
      border: 1px solid var(--neon-border);
      color: var(--neon);
      font-weight: 700;
      font-size: 0.9rem;
      transition: all 0.2s ease;
    }

    .game-link-btn:hover {
      background: var(--neon);
      color: #040705;
      box-shadow: 0 0 24px rgba(57, 255, 20, 0.35);
    }

    .team-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 18px;
    }

    .team-tag {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.74rem;
      padding: 6px 10px;
      border-radius: 8px;
      background: rgba(57, 255, 20, 0.07);
      border: 1px solid var(--neon-border);
      color: var(--neon-bright);
    }

    .team-status-note {
      padding: 12px 14px;
      border-radius: 12px;
      background: rgba(255, 255, 255, 0.02);
      border: 1px dashed var(--neon-border);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      color: var(--text-muted);
      text-align: center;
    }

    /* Portals-style 3 Pillars Section */
    .pillars-wrap {
      border-radius: 26px;
      background: linear-gradient(180deg, rgba(13, 20, 16, 0.9), rgba(7, 11, 8, 0.95));
      border: 1px solid var(--border-subtle);
      padding: 46px 38px;
    }

    .pillars-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 24px;
      margin-top: 32px;
    }

    .pillar-card {
      background: rgba(5, 8, 6, 0.65);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-md);
      padding: 26px;
      transition: border-color 0.25s ease, transform 0.25s ease;
    }

    .pillar-card:hover {
      border-color: var(--neon-border-strong);
      transform: translateY(-3px);
    }

    .pillar-num {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      font-weight: 700;
      color: var(--neon);
      margin-bottom: 12px;
    }

    .pillar-title {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.5rem;
      font-weight: 800;
      margin-bottom: 10px;
    }

    .pillar-desc {
      font-size: 0.92rem;
      line-height: 1.6;
      color: var(--text-muted);
    }

    /* Contact / Connect Section */
    .contact-card {
      position: relative;
      border-radius: 28px;
      background:
        radial-gradient(circle at 80% 20%, rgba(57, 255, 20, 0.16), transparent 45%),
        linear-gradient(145deg, #0d1610, #050806);
      border: 1px solid var(--neon-border);
      padding: 54px 42px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 32px;
      box-shadow: 0 24px 60px rgba(0, 0, 0, 0.55);
    }

    .contact-text h2 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(1.9rem, 3.4vw, 2.75rem);
      font-weight: 800;
      letter-spacing: -0.03em;
      margin-bottom: 12px;
    }

    .contact-text p {
      color: var(--text-muted);
      font-size: 1rem;
      max-width: 520px;
      line-height: 1.6;
    }

    .social-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .profile-btn {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      padding: 15px 24px;
      border-radius: 14px;
      font-weight: 700;
      font-size: 0.96rem;
      cursor: pointer;
      transition: all 0.22s ease;
    }

    .profile-btn-discord {
      background: var(--neon);
      color: #030604;
      border: 1px solid var(--neon);
      box-shadow: 0 0 28px rgba(57, 255, 20, 0.3);
    }

    .profile-btn-discord:hover {
      background: var(--neon-bright);
      transform: translateY(-2px);
      box-shadow: 0 0 38px rgba(57, 255, 20, 0.52);
    }

    .profile-btn-roblox {
      background: rgba(57, 255, 20, 0.08);
      color: var(--text-main);
      border: 1px solid var(--neon-border-strong);
    }

    .profile-btn-roblox:hover {
      background: rgba(57, 255, 20, 0.16);
      color: var(--neon);
      transform: translateY(-2px);
    }

    .handle-sub {
      display: block;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.72rem;
      opacity: 0.8;
      font-weight: 500;
    }

    /* Footer */
    footer {
      border-top: 1px solid var(--border-subtle);
      padding: 46px 0 38px;
      margin-top: 24px;
      background: rgba(4, 6, 5, 0.85);
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 1.5fr 1fr 1fr;
      gap: 32px;
      margin-bottom: 30px;
    }

    .footer-col h4 {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      color: var(--neon);
      margin-bottom: 14px;
    }

    .footer-col ul {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .footer-col a {
      color: var(--text-muted);
      font-size: 0.9rem;
      transition: color 0.2s ease;
    }

    .footer-col a:hover {
      color: var(--neon);
    }

    .footer-bottom {
      padding-top: 24px;
      border-top: 1px solid var(--border-subtle);
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 12px;
      font-size: 0.82rem;
      color: var(--text-dim);
      font-family: 'JetBrains Mono', monospace;
    }

    /* Toast Notification */
    .toast {
      position: fixed;
      bottom: 24px;
      right: 24px;
      z-index: 100;
      padding: 12px 18px;
      border-radius: 12px;
      background: #0a140d;
      border: 1px solid var(--neon);
      color: var(--neon);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.82rem;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.7), 0 0 20px rgba(57, 255, 20, 0.25);
      opacity: 0;
      transform: translateY(14px);
      pointer-events: none;
      transition: all 0.25s ease;
    }

    .toast.show {
      opacity: 1;
      transform: translateY(0);
    }

    /* Responsive */
    @media (max-width: 980px) {
      .hero-grid {
        grid-template-columns: 1fr;
      }
      .games-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
      .pillars-grid {
        grid-template-columns: 1fr;
      }
      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 680px) {
      .nav-links {
        display: none;
      }
      .games-grid {
        grid-template-columns: 1fr;
      }
      .hero-metrics {
        grid-template-columns: 1fr 1fr;
      }
      .contact-card {
        padding: 34px 24px;
      }
      .pillars-wrap {
        padding: 32px 22px;
      }
      .footer-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <header class="navbar">
    <div class="container nav-inner">
      <a href="#top" class="brand" aria-label="TIMMY Home">
        <img
          src="./timmy-logo.png"
          alt="TIMMY Logo"
          class="brand-logo"
          onerror="this.style.display='none'; document.getElementById('nav-logo-fallback').style.display='inline-flex';"
        />
        <span id="nav-logo-fallback" class="brand-fallback" style="display:none;">
          ⚡ TIMMY
        </span>
      </a>

      <nav class="nav-links">
        <a href="#top">Explore</a>
        <a href="#games">Games &amp; Teams</a>
        <a href="#workflow">What I Do</a>
        <a href="#Contact">Contact</a>
      </nav>

      <a href="#Contact" class="nav-cta">
        Hire / Connect
      </a>
    </div>
  </header>

  <!-- Hero Section -->
  <main id="top">
    <section class="hero">
      <div class="container hero-grid">
        <div>
          <div class="eyebrow">
            <span class="pulse-dot"></span>
            TIMMY // ROBLOX QA &amp; DISCORD MODERATION
          </div>

          <h1>
            Keeping Roblox games <span class="accent">clean, tested</span> &amp; thriving.
          </h1>

          <p class="hero-desc">
            I’m <strong>Timmy</strong>—a dedicated Roblox Game Tester and Discord Moderator working alongside hit experiences and development teams to catch bugs before players do and keep communities safe, active, and hype.
          </p>

          <div class="hero-actions">
            <a href="#games" class="btn btn-primary">
              Explore Experiences
            </a>
            <a href="#Contact" class="btn btn-secondary">
              Connect on Discord &amp; Roblox
            </a>
          </div>

          <div class="hero-metrics">
            <div class="metric-item">
              <div class="metric-val" id="hero-total-visits">475M<span>+</span></div>
              <div class="metric-label">Combined Game Visits</div>
            </div>
            <div class="metric-item">
              <div class="metric-val" id="hero-total-ccu">8,617<span>+</span></div>
              <div class="metric-label">Combined Live CCU</div>
            </div>
            <div class="metric-item">
              <div class="metric-val">QA <span>&amp;</span> MOD</div>
              <div class="metric-label">Testing &amp; Community Ops</div>
            </div>
          </div>
        </div>

        <div class="hero-showcase">
          <img
            src="./timmy-logo.png"
            alt="TIMMY Mascot Logo"
            class="hero-logo-img"
            onerror="this.style.display='none'; document.getElementById('hero-logo-fallback').style.display='block';"
          />
          <div id="hero-logo-fallback" style="display:none; margin-bottom:22px;">
            <svg width="240" height="110" viewBox="0 0 240 110" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="4" width="232" height="102" rx="22" fill="#061208" stroke="#39FF14" stroke-width="2.5"/>
              <text x="120" y="68" text-anchor="middle" fill="#39FF14" font-family="Space Grotesk, sans-serif" font-weight="800" font-size="44" letter-spacing="2">TIMMY</text>
            </svg>
          </div>
          <div class="showcase-badges">
            <span class="tag-pill">Roblox: varid2013</span>
            <span class="tag-pill">Discord: vm1th</span>
            <span class="tag-pill">Bug Hunting</span>
            <span class="tag-pill">Server Safety</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Games & Teams Section -->
    <section id="games">
      <div class="container">
        <div class="section-header">
          <div>
            <div class="section-kicker">// Portfolio &amp; Live Experience Data</div>
            <h2 class="section-title">Experiences I test &amp; moderate.</h2>
            <p class="section-sub">
              Live CCU and lifetime visits fetched straight from Roblox, refreshed every two minutes.
            </p>
          </div>

          <div class="live-sync-pill">
            <span class="pulse-dot"></span>
            <span id="sync-status">Syncing live stats...</span>
            <button type="button" class="refresh-btn" id="manual-refresh">Refresh</button>
          </div>
        </div>

        <div class="games-grid">

          <!-- Card 1: ROB IT -->
          <article class="game-card" data-place-id="96168869671905">
            <div class="game-thumb-wrap">
              <img
                src="./rob-it.jpg"
                alt="ROB IT Roblox Game Thumbnail"
                class="game-thumb"
                onerror="this.onerror=null; this.src='https://tr.rbxcdn.com/180DAY-c3f6764d7313a7e41b77dd6ad44e07bc/500/280/Image/Jpeg/noFilter';"
              />
              <span class="role-badge">Game Tester</span>
              <span class="live-chip">
                <span class="pulse-dot" style="width:6px;height:6px;"></span>
                LIVE
              </span>
            </div>

            <div class="game-body">
              <h3 class="game-title">ROB IT</h3>
              <p class="game-desc">
                High-stakes stealth &amp; heist experience—pick your mission, break in, steal the loot, and evade the guards. Actively playtested for gameplay polish, collision/map exploits, and mission flow.
              </p>

              <div class="stats-row">
                <div class="stat-box">
                  <div class="stat-label">Real-Time CCU</div>
                  <div class="stat-value neon" id="ccu-96168869671905">2,418</div>
                </div>
                <div class="stat-box">
                  <div class="stat-label">Total Visits</div>
                  <div class="stat-value" id="visits-96168869671905">314.8M+</div>
                </div>
              </div>

              <a
                href="https://www.roblox.com/games/96168869671905/ROB-IT"
                target="_blank"
                rel="noopener noreferrer"
                class="game-link-btn"
              >
                Play ROB IT on Roblox ↗
              </a>
            </div>
          </article>

          <!-- Card 2: Break a Brainrot Egg! -->
          <article class="game-card" data-place-id="119271610514030">
            <div class="game-thumb-wrap">
              <img
                src="./brainrot-egg.jpg"
                alt="Break a Brainrot Egg Roblox Game Thumbnail"
                class="game-thumb"
                onerror="this.onerror=null; this.src='https://tr.rbxcdn.com/180DAY-809ee5878b0ee380f7f4f237b4b1a33d/768/432/Image/Webp/noFilter';"
              />
              <span class="role-badge">Discord Moderator</span>
              <span class="live-chip">
                <span class="pulse-dot" style="width:6px;height:6px;"></span>
                LIVE
              </span>
            </div>

            <div class="game-body">
              <h3 class="game-title">Break a Brainrot Egg!</h3>
              <p class="game-desc">
                Viral incremental simulator where players crack Lucky Eggs, collect rare Brainrots, level up income, and rebirth. Moderating the official Discord community, live Admin Abuse events, and player tickets.
              </p>

              <div class="stats-row">
                <div class="stat-box">
                  <div class="stat-label">Real-Time CCU</div>
                  <div class="stat-value neon" id="ccu-119271610514030">6,199</div>
                </div>
                <div class="stat-box">
                  <div class="stat-label">Total Visits</div>
                  <div class="stat-value" id="visits-119271610514030">160.5M+</div>
                </div>
              </div>

              <a
                href="https://www.roblox.com/games/119271610514030/Break-a-Brainrot-Egg"
                target="_blank"
                rel="noopener noreferrer"
                class="game-link-btn"
              >
                Play Break a Brainrot Egg ↗
              </a>
            </div>
          </article>

          <!-- Card 3: WAVE BYTE GAMES (Testing Team - no image or link) -->
          <article class="game-card">
            <div class="game-thumb-wrap">
              <div class="wavebyte-banner">
                <div class="wavebyte-emblem" aria-hidden="true">
                  <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M2 12c2-4 4-4 6 0s4 4 6 0 4-4 6 0"/>
                    <path d="M2 17c2-4 4-4 6 0s4 4 6 0 4-4 6 0" opacity="0.5"/>
                  </svg>
                </div>
                <div class="wavebyte-title-art">WAVE <span>BYTE</span> GAMES</div>
              </div>
              <span class="role-badge">QA Testing Team</span>
            </div>

            <div class="game-body">
              <h3 class="game-title">WAVE BYTE GAMES</h3>
              <p class="game-desc">
                Active QA Tester inside the <strong>Wave Byte Games</strong> testing team—the studio behind hit Roblox titles like <strong>Jump for Animals</strong> and more. Focused on pre-release update testing, bug hunting, and gameplay balance.
              </p>

              <div class="team-tags">
                <span class="team-tag">Jump for Animals</span>
                <span class="team-tag">&amp; More Titles</span>
                <span class="team-tag">Pre-Update QA</span>
                <span class="team-tag">Bug Reports</span>
              </div>

              <div class="team-status-note">
                Internal QA Testing Team • Private Builds
              </div>
            </div>
          </article>

        </div>
      </div>
    </section>

    <!-- Portals-style 3-Pillar Section -->
    <section id="workflow">
      <div class="container">
        <div class="pillars-wrap">
          <div class="section-kicker">// How I Work</div>
          <h2 class="section-title">Sharp eyes. Safe communities.</h2>
          <p class="section-sub">
            Whether it’s breaking mechanics before launch or keeping thousands of Discord members in check during update drops.
          </p>

          <div class="pillars-grid">
            <div class="pillar-card">
              <div class="pillar-num">01 // TEST</div>
              <h3 class="pillar-title">Break.</h3>
              <p class="pillar-desc">
                Stress-testing new updates, reproducing edge-case bugs, checking progression &amp; economy balance, and writing clear reports devs can fix fast.
              </p>
            </div>

            <div class="pillar-card">
              <div class="pillar-num">02 // MODERATE</div>
              <h3 class="pillar-title">Protect.</h3>
              <p class="pillar-desc">
                Keeping Discord servers clean, fair, and scam-free—handling tickets, enforcing rules calmly, and managing heavy traffic during Admin Abuse &amp; live events.
              </p>
            </div>

            <div class="pillar-card">
              <div class="pillar-num">03 // SUPPORT</div>
              <h3 class="pillar-title">Elevate.</h3>
              <p class="pillar-desc">
                Acting as the bridge between players and developers by surfacing community feedback, patch-day issues, and ideas that keep players coming back.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="Contact">
      <div class="container">
        <div class="contact-card">
          <div class="contact-text">
            <div class="section-kicker">// Get In Touch</div>
            <h2>Need a reliable QA tester or mod?</h2>
            <p>
              Reach out directly on Discord or check out my Roblox profile. Always down to help test upcoming updates or moderate growing communities.
            </p>
          </div>

          <div class="social-buttons">
            <!-- Discord Button -->
            <a
              id="discord-profile-btn"
              href="https://discord.com/app"
              target="_blank"
              rel="noopener noreferrer"
              class="profile-btn profile-btn-discord"
            >
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
                <path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994.021-.041.001-.09-.041-.106a13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.061 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.028zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/>
              </svg>
              <span>
                Discord Profile
                <span class="handle-sub">@vm1th</span>
              </span>
            </a>

            <!-- Roblox Button -->
            <a
              id="roblox-profile-btn"
              href="https://www.roblox.com/search/users?keyword=varid2013"
              target="_blank"
              rel="noopener noreferrer"
              class="profile-btn profile-btn-roblox"
            >
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
                <path d="M5.164 0L.16 18.928 18.836 24 23.84 5.072 5.164 0zm8.747 14.23l-4.14-1.094 1.094-4.14 4.14 1.094-1.094 4.14z"/>
              </svg>
              <span>
                Roblox Profile
                <span class="handle-sub">@varid2013</span>
              </span>
            </a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- Footer -->
  <footer>
    <div class="container">
      <div class="footer-grid">
        <div class="footer-col">
          <div class="brand" style="margin-bottom:12px;">
            <span class="brand-fallback" style="font-size:1.25rem;">⚡ TIMMY</span>
          </div>
          <p style="color: var(--text-muted); font-size:0.88rem; line-height:1.6; max-width:340px;">
            Roblox Game Tester &amp; Discord Moderator helping studios ship cleaner experiences and maintain strong communities.
          </p>
        </div>

        <div class="footer-col">
          <h4>Explore</h4>
          <ul>
            <li><a href="#games">Games &amp; Teams</a></li>
            <li><a href="#workflow">What I Do</a></li>
            <li><a href="#Contact">Contact</a></li>
          </ul>
        </div>

        <div class="footer-col">
          <h4>Connect</h4>
          <ul>
            <li><a href="#Contact" onclick="document.getElementById('discord-profile-btn').click(); return false;">Discord (vm1th)</a></li>
            <li><a id="footer-roblox-link" href="https://www.roblox.com/search/users?keyword=varid2013" target="_blank" rel="noopener noreferrer">Roblox (varid2013)</a></li>
          </ul>
        </div>
      </div>

      <div class="footer-bottom">
        <span>© <span id="year"></span> TIMMY Portfolio. Built for Roblox QA &amp; Moderation.</span>
        <span>Live stats synced via Roblox API</span>
      </div>
    </div>
  </footer>

  <div id="toast" class="toast"></div>

  <script>
    // =========================================================
    // CONFIG — Optional: Paste your numeric Discord User ID here
    // (Right-click your profile in Discord with Developer Mode on -> Copy User ID)
    // Once added, the Discord button links straight to discord.com/users/YOUR_ID
    // =========================================================
    const DISCORD_USERNAME = "vm1th";
    const DISCORD_USER_ID = ""; // e.g. "123456789012345678"
    const ROBLOX_USERNAME = "varid2013";

    const GAMES = [
      {
        placeId: "96168869671905",
        name: "ROB IT",
        fallbackCcu: 2418,
        fallbackVisits: 314800000
      },
      {
        placeId: "119271610514030",
        name: "Break a Brainrot Egg!",
        fallbackCcu: 6199,
        fallbackVisits: 160500000
      }
    ];

    document.getElementById("year").textContent = new Date().getFullYear();

    function showToast(msg) {
      const toast = document.getElementById("toast");
      toast.textContent = msg;
      toast.classList.add("show");
      setTimeout(() => toast.classList.remove("show"), 3200);
    }

    function formatNumber(num) {
      return Number(num).toLocaleString("en-US");
    }

    function formatVisits(visits) {
      if (visits >= 1_000_000_000) return (visits / 1_000_000_000).toFixed(2) + "B+";
      if (visits >= 1_000_000) return (visits / 1_000_000).toFixed(1) + "M+";
      if (visits >= 1_000) return (visits / 1_000).toFixed(1) + "K+";
      return formatNumber(visits);
    }

    // Discord button behavior:
    // Links directly to profile if DISCORD_USER_ID is provided;
    // otherwise copies username & opens Discord cleanly.
    const discordBtn = document.getElementById("discord-profile-btn");
    if (DISCORD_USER_ID.trim()) {
      discordBtn.href = `https://discord.com/users/${DISCORD_USER_ID.trim()}`;
    } else {
      discordBtn.addEventListener("click", (e) => {
        if (navigator.clipboard) {
          navigator.clipboard.writeText(DISCORD_USERNAME).catch(() => {});
        }
        showToast(`Copied Discord "${DISCORD_USERNAME}"! Opening Discord...`);
      });
    }

    // Dynamically resolve Roblox User ID for varid2013 so button goes directly to profile
    async function resolveRobloxProfile() {
      try {
        const res = await fetch("https://users.roproxy.com/v1/usernames/users", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({
            usernames: [ROBLOX_USERNAME],
            excludeBannedUsers: false
          })
        });
        if (!res.ok) return;
        const json = await res.json();
        if (json.data && json.data.length > 0) {
          const userId = json.data[0].id;
          const profileUrl = `https://www.roblox.com/users/${userId}/profile`;
          document.getElementById("roblox-profile-btn").href = profileUrl;
          document.getElementById("footer-roblox-link").href = profileUrl;
        }
      } catch (_) {
        // Fallback link to Roblox user search remains active
      }
    }

    // Fetch live CCU and Visits from Roblox via RoProxy
    async function fetchLiveGameStats() {
      const statusEl = document.getElementById("sync-status");
      statusEl.textContent = "Fetching live Roblox numbers...";

      let totalCcu = 0;
      let totalVisits = 0;
      let liveCount = 0;

      try {
        const universeEntries = await Promise.all(
          GAMES.map(async (g) => {
            const uRes = await fetch(`https://apis.roproxy.com/universes/v1/places/${g.placeId}/universe`);
            if (!uRes.ok) throw new Error("Universe lookup failed");
            const uData = await uRes.json();
            return { ...g, universeId: uData.universeId };
          })
        );

        const universeIds = universeEntries.map((g) => g.universeId).join(",");
        const gamesRes = await fetch(`https://games.roproxy.com/v1/games?universeIds=${universeIds}`);
        if (!gamesRes.ok) throw new Error("Games fetch failed");
        const gamesJson = await gamesRes.json();

        universeEntries.forEach((entry) => {
          const liveGame = gamesJson.data.find((d) => d.id === entry.universeId);
          const ccuEl = document.getElementById(`ccu-${entry.placeId}`);
          const visitsEl = document.getElementById(`visits-${entry.placeId}`);

          if (liveGame) {
            const ccu = liveGame.playing ?? entry.fallbackCcu;
            const visits = liveGame.visits ?? entry.fallbackVisits;
            ccuEl.textContent = formatNumber(ccu);
            visitsEl.textContent = formatVisits(visits);
            totalCcu += ccu;
            totalVisits += visits;
            liveCount++;
          }
        });

        if (liveCount > 0) {
          document.getElementById("hero-total-ccu").innerHTML = `${formatNumber(totalCcu)}<span>+</span>`;
          document.getElementById("hero-total-visits").innerHTML = `${formatVisits(totalVisits).replace("+", "")}<span>+</span>`;
          const now = new Date().toLocaleTimeString([], { hour: "2-digit", minute: "2-digit" });
          statusEl.textContent = `Live Roblox API • Updated ${now}`;
          return;
        }
      } catch (err) {
        // Graceful fallback to latest verified snapshot values
        GAMES.forEach((entry) => {
          totalCcu += entry.fallbackCcu;
          totalVisits += entry.fallbackVisits;
        });
        document.getElementById("hero-total-ccu").innerHTML = `${formatNumber(totalCcu)}<span>+</span>`;
        document.getElementById("hero-total-visits").innerHTML = `${formatVisits(totalVisits).replace("+", "")}<span>+</span>`;
        statusEl.textContent = "Cached stats active (open via server/online for live sync)";
      }
    }

    document.getElementById("manual-refresh").addEventListener("click", fetchLiveGameStats);

    // Initial load + 2-minute live refresh (like Portals)
    resolveRobloxProfile();
    fetchLiveGameStats();
    setInterval(fetchLiveGameStats, 120000);
  </script>
</body>
</html>

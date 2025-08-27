<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>PROJECT_NAME — README</title>
  <meta name="description" content="Concise, beautiful, single‑file HTML README template." />
  <style>
    /* ----- CSS Variables & Theme ----- */
    :root {
      --bg: #0b1020;
      --panel: #0f162e;
      --text: #e9eefb;
      --muted: #b9c1dc;
      --brand-1: #7c8cf8;
      --brand-2: #64d6ee;
      --brand-3: #67f7a1;
      --accent: #f6a6ff;
      --link: #8cc4ff;
      --code-bg: #0a0f1f;
      --border: #1b244a;
      --shadow: 0 10px 30px rgba(8,12,34,.35);
    }
    @media (prefers-color-scheme: light) {
      :root {
        --bg: #f7f9ff;
        --panel: #ffffff;
        --text: #0c1635;
        --muted: #4f5b83;
        --brand-1: #4855ff;
        --brand-2: #00a6d6;
        --brand-3: #1fbf66;
        --accent: #b800d8;
        --link: #0d63c3;
        --code-bg: #f3f5ff;
        --border: #e4e8fb;
        --shadow: 0 12px 24px rgba(22,35,81,.1);
      }
    }
    [data-theme="light"] {
      --bg: #f7f9ff;
      --panel: #ffffff;
      --text: #0c1635;
      --muted: #4f5b83;
      --brand-1: #4855ff;
      --brand-2: #00a6d6;
      --brand-3: #1fbf66;
      --accent: #b800d8;
      --link: #0d63c3;
      --code-bg: #f3f5ff;
      --border: #e4e8fb;
      --shadow: 0 12px 24px rgba(22,35,81,.1);
    }

    /* ----- Base ----- */
    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body {
      margin: 0;
      font: 16px/1.65 system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      color: var(--text);
      background: radial-gradient(1200px 600px at 10% -10%, rgba(124,140,248,.25), transparent 60%),
                  radial-gradient(1200px 600px at 90% 10%, rgba(100,214,238,.18), transparent 60%),
                  linear-gradient(180deg, var(--bg), #060916 80%);
      padding: 0 1rem 4rem;
    }
    a { color: var(--link); text-decoration: none; }
    a:hover { text-decoration: underline; }
    .container { max-width: 980px; margin: 0 auto; }

    /* ----- Header / Hero ----- */
    .hero {
      position: relative;
      margin: 2.5rem auto 2rem;
      padding: 2rem;
      border-radius: 20px;
      background:
        radial-gradient(1200px 400px at 100% -10%, rgba(103,247,161,.2), transparent 60%),
        linear-gradient(135deg, rgba(124,140,248,.25), rgba(100,214,238,.2) 40%, rgba(246,166,255,.12));
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      overflow: hidden;
    }
    .hero h1 {
      margin: 0 0 .35rem;
      font-size: clamp(1.8rem, 4vw, 2.6rem);
      line-height: 1.15;
      letter-spacing: .3px;
    }
    .hero p {
      margin: 0.25rem 0 1rem;
      color: var(--muted);
      max-width: 65ch;
    }
    .kickers { display: flex; flex-wrap: wrap; gap: .5rem; margin: .75rem 0 0; }
    .badge {
      display: inline-flex; align-items: center; gap: .4rem;
      padding: .35rem .6rem; border-radius: 999px;
      border: 1px solid var(--border);
      background: color-mix(in hsl, var(--panel) 80%, var(--brand-1));
      font-size: .8rem; color: var(--text);
    }
    .badge svg { opacity: .9 }

    /* Controls */
    .controls { display: flex; gap: .6rem; align-items: center; margin-top: 1rem; }
    .btn {
      display: inline-flex; align-items: center; gap: .5rem;
      padding: .6rem .9rem; border-radius: 12px;
      border: 1px solid var(--border);
      background: linear-gradient(180deg, color-mix(in oklab, var(--panel) 80%, white 10%), var(--panel));
      color: var(--text); text-decoration: none; font-weight: 600;
      box-shadow: var(--shadow);
    }
    .btn:hover { transform: translateY(-1px); }
    .btn.primary { background: linear-gradient(135deg, var(--brand-1), var(--brand-2)); border: none; color: white; }

    /* Theme toggle */
    .toggle { margin-left: auto; display: inline-flex; align-items:center; gap:.5rem; }
    .switch { position: relative; width: 44px; height: 26px; background: var(--panel); border: 1px solid var(--border); border-radius: 999px; }
    .switch i { position: absolute; top: 2px; left: 2px; width: 20px; height: 20px; border-radius: 50%; background: linear-gradient(135deg, var(--brand-2), var(--brand-3)); transition: transform .25s ease; }
    body[data-theme="light"] .switch i { transform: translateX(18px); background: linear-gradient(135deg, var(--brand-1), var(--accent)); }

    /* ----- Main Card Sections ----- */
    section.card {
      background: var(--panel);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      border-radius: 18px;
      padding: 1.25rem 1.25rem 1.5rem;
      margin: 1rem 0;
    }
    section.card h2 { margin-top: 0; font-size: 1.35rem; }
    .grid { display: grid; gap: 1rem; }
    @media (min-width: 850px) { .grid-2 { grid-template-columns: 1fr 1fr; } }

    /* Lists, tables */
    ul, ol { padding-left: 1.2rem; }
    table { width: 100%; border-collapse: collapse; border: 1px solid var(--border); border-radius: 14px; overflow: hidden; }
    thead th { text-align: left; font-size: .9rem; color: var(--muted); background: color-mix(in hsl, var(--panel), black 6%); }
    td, th { padding: .7rem .8rem; border-bottom: 1px solid var(--border); }

    /* Code */
    code { background: var(--code-bg); padding: .12rem .4rem; border-radius: .4rem; border: 1px solid var(--border); font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace; font-size: 0.95em; }
    pre { background: var(--code-bg); padding: 1rem; border-radius: 12px; border: 1px solid var(--border); position: relative; overflow: auto; }
    pre code { padding: 0; border: 0; background: transparent; }
    .copy-btn { position: absolute; top: 10px; right: 10px; border: 1px solid var(--border); border-radius: 10px; padding: .35rem .6rem; background: var(--panel); cursor: pointer; }

    /* Callouts */
    .callout { border: 1px solid var(--border); border-left: 4px solid var(--brand-2); padding: .9rem 1rem; border-radius: 12px; background: color-mix(in hsl, var(--panel) 80%, var(--brand-2) 10%); }
    .callout.warn { border-left-color: #ffb545; background: color-mix(in hsl, var(--panel) 80%, #ffb545 10%); }
    .callout.danger { border-left-color: #ff6b86; background: color-mix(in hsl, var(--panel) 80%, #ff6b86 12%); }

    /* Footer */
    footer { margin: 2rem 0 0; color: var(--muted); font-size: .95rem; text-align: center; }
  </style>
</head>
<body>
  <div class="container">
    <header class="hero">
      <div class="kickers">
        <span class="badge" title="Project Status">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87L18.18 22 12 18.77 5.82 22 7 14.14l-5-4.87 6.91-1.01L12 2z" stroke="currentColor"/></svg>
          <strong>Stable</strong> · v1.0.0
        </span>
        <span class="badge" title="License">MIT</span>
        <span class="badge" title="Language">TypeScript</span>
      </div>
      <h1>PROJECT_NAME</h1>
      <p><em>One‑line description</em> — Replace this with a concise summary (what it does, who it’s for). Keep it under ~120 characters.</p>
      <div class="controls">
        <a class="btn primary" href="#installation">Get Started</a>
        <a class="btn" href="#usage">Usage</a>
        <label class="toggle" title="Toggle theme">
          <span>Light</span>
          <span class="switch"><i></i></span>
        </label>
      </div>
    </header>

    <section class="card" id="badges">
      <h2>Badges</h2>
      <p>Swap these for real shields if you like:</p>
      <p>
        <img alt="build" src="https://img.shields.io/badge/build-passing-brightgreen"> 
        <img alt="coverage" src="https://img.shields.io/badge/coverage-98%25-blue"> 
        <img alt="license" src="https://img.shields.io/badge/license-MIT-purple"> 
        <img alt="issues" src="https://img.shields.io/badge/issues-0-success">
      </p>
    </section>

    <section class="card" id="toc">
      <h2>Table of Contents</h2>
      <div class="grid grid-2">
        <ol>
          <li><a href="#features">Features</a></li>
          <li><a href="#installation">Installation</a></li>
          <li><a href="#usage">Usage</a></li>
          <li><a href="#configuration">Configuration</a></li>
          <li><a href="#screenshots">Screenshots</a></li>
        </ol>
        <ol start="6">
          <li><a href="#api">API</a></li>
          <li><a href="#faq">FAQ</a></li>
          <li><a href="#contributing">Contributing</a></li>
          <li><a href="#license">License</a></li>
          <li><a href="#acknowledgments">Acknowledgments</a></li>
        </ol>
      </div>
    </section>

    <section class="card" id="features">
      <h2>Features</h2>
      <ul>
        <li>✨ Clean, single‑file HTML README with dark/light theme</li>
        <li>🎯 Copy‑to‑clipboard buttons for code blocks</li>
        <li>🧩 Responsive layout with card sections</li>
        <li>🧪 Ready‑to‑fill badges, sections, and callouts</li>
        <li>🔗 In‑page anchor navigation</li>
      </ul>
      <div class="callout">
        Pro tip: keep paragraphs short and front‑load the key takeaway.
      </div>
    </section>

    <section class="card" id="installation">
      <h2>Installation</h2>
      <ol>
        <li>Ensure you have <code>node &gt;= 18</code> and <code>pnpm</code> or <code>npm</code> installed.</li>
        <li>Install the package:
          <pre><button class="copy-btn" data-copy>Copy</button><code>pnpm add PROJECT_PACKAGE
# or
npm i PROJECT_PACKAGE</code></pre>
        </li>
        <li>Initialize the project:
          <pre><button class="copy-btn" data-copy>Copy</button><code>npx PROJECT_CLI init my-app</code></pre>
        </li>
      </ol>
      <div class="callout warn">If you see permission errors on macOS/Linux, prefix with <code>sudo</code> or fix your <code>npm</code> prefix path.</div>
    </section>

    <section class="card" id="usage">
      <h2>Usage</h2>
      <p>Basic example:</p>
      <pre><button class="copy-btn" data-copy>Copy</button><code>// main.ts
import { awesome } from "project";

awesome({
  input: "./src",
  outDir: "./dist",
  watch: true,
});</code></pre>
      <div class="grid grid-2">
        <div>
          <h3>CLI</h3>
          <pre><button class="copy-btn" data-copy>Copy</button><code>project build --minify --sourcemap</code></pre>
        </div>
        <div>
          <h3>Config</h3>
          <pre><button class="copy-btn" data-copy>Copy</button><code>// project.config.json
{
  "minify": true,
  "sourcemap": true,
  "targets": ["es2022"]
}</code></pre>
        </div>
      </div>
    </section>

    <section class="card" id="configuration">
      <h2>Configuration</h2>
      <table>
        <thead>
          <tr><th>Option</th><th>Type</th><th>Default</th><th>Description</th></tr>
        </thead>
        <tbody>
          <tr><td><code>outDir</code></td><td>string</td><td><code>dist</code></td><td>Output directory</td></tr>
          <tr><td><code>watch</code></td><td>boolean</td><td><code>false</code></td><td>Watch files for changes</td></tr>
          <tr><td><code>minify</code></td><td>boolean</td><td><code>false</code></td><td>Minify output</td></tr>
          <tr><td><code>targets</code></td><td>string[]</td><td><code>["es2022"]</code></td><td>Compilation targets</td></tr>
        </tbody>
      </table>
    </section>

    <section class="card" id="screenshots">
      <h2>Screenshots</h2>
      <p>Drop in your images. The figure below is a placeholder.</p>
      <figure style="margin:0; padding:0;">
        <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?q=80&w=1200&auto=format&fit=crop" alt="Screenshot placeholder" style="width:100%; border-radius: 12px; border:1px solid var(--border);" />
        <figcaption style="color:var(--muted); font-size:.9rem; margin-top:.4rem;">A clean, generous screenshot caption.</figcaption>
      </figure>
    </section>

    <section class="card" id="api">
      <h2>API</h2>
      <h3><code>awesome(options: AwesomeOptions): Promise&lt;void&gt;</code></h3>
      <p>Runs the main pipeline.</p>
      <pre><button class="copy-btn" data-copy>Copy</button><code>type AwesomeOptions = {
  input: string;
  outDir?: string;
  minify?: boolean;
  watch?: boolean;
};</code></pre>
    </section>

    <section class="card" id="faq">
      <h2>FAQ</h2>
      <details open>
        <summary><strong>Is this really a README?</strong></summary>
        <p>Yep—just a fancy one, meant to live in your repo or docs site and still be printable or shareable as a single HTML file.</p>
      </details>
      <details>
        <summary><strong>Can I use Markdown?</strong></summary>
        <p>Totally. This template is for when you want full‑control theming without a build step. You can convert Markdown to HTML when publishing.</p>
      </details>
      <details>
        <summary><strong>How do I change the accent colors?</strong></summary>
        <p>Tweak the CSS variables at the top (e.g., <code>--brand-1</code>, <code>--brand-2</code>, <code>--brand-3</code>).</p>
      </details>
    </section>

    <section class="card" id="contributing">
      <h2>Contributing</h2>
      <ol>
        <li>Fork the repo</li>
        <li>Create a branch: <code>git checkout -b feat/your-feature</code></li>
        <li>Commit changes: <code>git commit -m "feat: add your feature"</code></li>
        <li>Open a PR 🎉</li>
      </ol>
      <div class="callout danger">Please follow the Code of Conduct and write tests for new features.</div>
    </section>

    <section class="card" id="license">
      <h2>License</h2>
      <p>Licensed under the <a href="#">MIT License</a> — see <code>LICENSE</code> for details.</p>
    </section>

    <section class="card" id="acknowledgments">
      <h2>Acknowledgments</h2>
      <ul>
        <li>Inspired by the open‑source community 💜</li>
        <li>Unsplash for placeholder imagery</li>
        <li>You, for shipping great things</li>
      </ul>
    </section>

    <footer>
      <p>© YOUR_NAME — <a href="mailto:you@example.com">you@example.com</a> · <a href="#">Website</a> · <a href="#">Twitter</a></p>
    </footer>
  </div>

  <script>
    // Theme toggle
    const toggle = document.querySelector('.toggle');
    toggle?.addEventListener('click', () => {
      const isLight = document.body.getAttribute('data-theme') === 'light';
      document.body.setAttribute('data-theme', isLight ? '' : 'light');
    });

    // Copy-to-clipboard for code blocks
    document.querySelectorAll('[data-copy]').forEach((btn) => {
      btn.addEventListener('click', async () => {
        const code = btn.nextElementSibling?.innerText || '';
        try {
          await navigator.clipboard.writeText(code);
          const original = btn.textContent;
          btn.textContent = 'Copied!';
          setTimeout(() => (btn.textContent = original), 1200);
        } catch (e) {
          console.error('Copy failed', e);
        }
      });
    });
  </script>
</body>
</html>

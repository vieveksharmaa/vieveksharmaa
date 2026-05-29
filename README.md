<div align="center">

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                  ANIMATED N8N WORKFLOW SVG                  -->
<!-- ═══════════════════════════════════════════════════════════ -->

<svg width="800" height="320" viewBox="0 0 800 320" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <style>
      .bg { fill: #0D0B12; }
      .node-box { rx: 10; ry: 10; }
      .node-label { font-family: 'Segoe UI', Arial, sans-serif; font-size: 11px; font-weight: 600; fill: #F0EEF8; text-anchor: middle; }
      .node-sub   { font-family: 'Segoe UI', Arial, sans-serif; font-size: 9px;  font-weight: 400; fill: rgba(240,238,248,0.45); text-anchor: middle; }
      .edge       { fill: none; stroke-width: 1.5; stroke-dasharray: 4 4; opacity: 0.35; }
      .title      { font-family: 'Segoe UI', Arial, sans-serif; font-size: 15px; font-weight: 700; fill: #EA4B71; text-anchor: middle; letter-spacing: 0.5px; }
      .subtitle   { font-family: 'Segoe UI', Arial, sans-serif; font-size: 11px; font-weight: 400; fill: rgba(240,238,248,0.45); text-anchor: middle; }
      .timer-lbl  { font-family: 'Courier New', monospace; font-size: 12px; font-weight: 700; fill: #68D391; text-anchor: middle; }
      .timer-sub  { font-family: 'Segoe UI', Arial, sans-serif; font-size: 10px; fill: rgba(240,238,248,0.35); text-anchor: middle; }
      .saved-lbl  { font-family: 'Segoe UI', Arial, sans-serif; font-size: 11px; font-weight: 600; fill: #F6AD55; text-anchor: middle; }

      /* NODE PULSE ANIMATIONS — each node lights up in turn */
      @keyframes pulse0 { 0%,8%,100%{opacity:1} 4%{opacity:0.25} }
      @keyframes pulse1 { 0%,16%,100%{opacity:0.3} 12%,20%{opacity:1} }
      @keyframes pulse2 { 0%,28%,100%{opacity:0.3} 24%,32%{opacity:1} }
      @keyframes pulse3 { 0%,40%,100%{opacity:0.3} 36%,44%{opacity:1} }
      @keyframes pulse4 { 0%,52%,100%{opacity:0.3} 48%,56%{opacity:1} }
      @keyframes pulse5 { 0%,64%,100%{opacity:0.3} 60%,68%{opacity:1} }

      .n0 { animation: pulse0 4s ease-in-out infinite; }
      .n1 { animation: pulse1 4s ease-in-out infinite; }
      .n2 { animation: pulse2 4s ease-in-out infinite; }
      .n3 { animation: pulse3 4s ease-in-out infinite; }
      .n4 { animation: pulse4 4s ease-in-out infinite; }
      .n5 { animation: pulse5 4s ease-in-out infinite; }

      /* PACKET — small glowing dot travelling left to right */
      @keyframes travel0 { 0%{transform:translateX(0px)} 8%{transform:translateX(87px)} 100%{transform:translateX(87px)} }
      @keyframes travel1 { 0%,10%{transform:translateX(0px)} 18%{transform:translateX(87px)} 100%{transform:translateX(87px)} }
      @keyframes travel2 { 0%,22%{transform:translateX(0px)} 30%{transform:translateX(87px)} 100%{transform:translateX(87px)} }
      @keyframes travel3 { 0%,34%{transform:translateX(0px)} 42%{transform:translateX(87px)} 100%{transform:translateX(87px)} }
      @keyframes travel4 { 0%,46%{transform:translateX(0px)} 54%{transform:translateX(87px)} 100%{transform:translateX(87px)} }

      .pkt0 { animation: travel0 4s linear infinite; }
      .pkt1 { animation: travel1 4s linear infinite; }
      .pkt2 { animation: travel2 4s linear infinite; }
      .pkt3 { animation: travel3 4s linear infinite; }
      .pkt4 { animation: travel4 4s linear infinite; }

      /* EDGE GLOW — active edge flashes when packet passes */
      @keyframes eglow0 { 0%,6%,100%{opacity:0.35} 3%{opacity:0.9} }
      @keyframes eglow1 { 0%,18%,100%{opacity:0.35} 14%{opacity:0.9} }
      @keyframes eglow2 { 0%,30%,100%{opacity:0.35} 26%{opacity:0.9} }
      @keyframes eglow3 { 0%,42%,100%{opacity:0.35} 38%{opacity:0.9} }
      @keyframes eglow4 { 0%,54%,100%{opacity:0.35} 50%{opacity:0.9} }

      .eg0 { animation: eglow0 4s ease-in-out infinite; }
      .eg1 { animation: eglow1 4s ease-in-out infinite; }
      .eg2 { animation: eglow2 4s ease-in-out infinite; }
      .eg3 { animation: eglow3 4s ease-in-out infinite; }
      .eg4 { animation: eglow4 4s ease-in-out infinite; }

      /* TIMER TICK */
      @keyframes tick {
        0%  { opacity:0 }
        5%  { opacity:1 }
        70% { opacity:1 }
        80%,100% { opacity:0 }
      }
      .t0 { animation: tick 4s 0.0s ease-in-out infinite; }
      .t1 { animation: tick 4s 0.6s ease-in-out infinite; }
      .t2 { animation: tick 4s 1.2s ease-in-out infinite; }
      .t3 { animation: tick 4s 1.8s ease-in-out infinite; }
      .t4 { animation: tick 4s 2.4s ease-in-out infinite; }
      .t5 { animation: tick 4s 3.0s ease-in-out infinite; }

      /* DONE CHECKMARK */
      @keyframes done { 0%,70%{opacity:0;transform:scale(0.5)} 80%,95%{opacity:1;transform:scale(1)} 100%{opacity:0} }
      .done-mark { animation: done 4s ease-in-out infinite; transform-origin: 683px 148px; }

      /* HEADER GLOW */
      @keyframes hglow { 0%,100%{opacity:0.8} 50%{opacity:1} }
      .hglow { animation: hglow 3s ease-in-out infinite; }
    </style>

    <!-- GLOW FILTER -->
    <filter id="glow" x="-30%" y="-30%" width="160%" height="160%">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="glow-strong" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>

    <!-- GRID PATTERN -->
    <pattern id="grid" width="20" height="20" patternUnits="userSpaceOnUse">
      <path d="M 20 0 L 0 0 0 20" fill="none" stroke="rgba(255,255,255,0.03)" stroke-width="0.5"/>
    </pattern>

    <!-- NODE GRADIENT -->
    <linearGradient id="ng0" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#1A0F2E"/><stop offset="100%" stop-color="#2D1052"/></linearGradient>
    <linearGradient id="ng1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#0F1A0F"/><stop offset="100%" stop-color="#1A3020"/></linearGradient>
  </defs>

  <!-- BG -->
  <rect width="800" height="320" fill="#0D0B12" rx="12"/>
  <rect width="800" height="320" fill="url(#grid)" rx="12"/>

  <!-- AMBIENT GLOW -->
  <ellipse cx="400" cy="160" rx="280" ry="100" fill="rgba(234,75,113,0.04)"/>

  <!-- TITLE -->
  <text x="400" y="36" class="title hglow">⚡ n8n Automation Pipeline</text>
  <text x="400" y="54" class="subtitle">Payment received → AI processes → WhatsApp sent → Certificate delivered · in 4.2 seconds</text>

  <!-- ══════════ EDGES ══════════ -->
  <!-- Edge 0: Node0 → Node1 -->
  <line x1="133" y1="148" x2="193" y2="148" stroke="#EA4B71" class="edge eg0"/>
  <!-- Edge 1: Node1 → Node2 -->
  <line x1="280" y1="148" x2="340" y2="148" stroke="#EA4B71" class="edge eg1"/>
  <!-- Edge 2: Node2 → Node3 -->
  <line x1="427" y1="148" x2="487" y2="148" stroke="#EA4B71" class="edge eg2"/>
  <!-- Edge 3: Node3 → Node4 -->
  <line x1="574" y1="148" x2="634" y2="148" stroke="#EA4B71" class="edge eg3"/>
  <!-- Edge 4: Node4 → Node5 -->
  <line x1="720" y1="148" x2="760" y2="148" stroke="#68D391" class="edge eg4"/>

  <!-- ══════════ NODES ══════════ -->

  <!-- NODE 0: Webhook Trigger -->
  <g class="n0">
    <rect x="30" y="118" width="103" height="60" rx="8" fill="url(#ng0)" stroke="#EA4B71" stroke-width="1.5" filter="url(#glow)"/>
    <text x="81" y="140" class="node-label">🔗 Webhook</text>
    <text x="81" y="153" class="node-sub">Razorpay</text>
    <text x="81" y="164" class="node-sub">Payment Event</text>
  </g>

  <!-- NODE 1: n8n Core -->
  <g class="n1">
    <rect x="193" y="112" width="87" height="72" rx="8" fill="#1A0B1E" stroke="#EA4B71" stroke-width="2" filter="url(#glow-strong)"/>
    <text x="236" y="140" class="node-label" style="fill:#EA4B71;font-size:13px">⚡ n8n</text>
    <text x="236" y="155" class="node-sub">Route &amp; Filter</text>
    <text x="236" y="167" class="node-sub">Switch Node</text>
  </g>

  <!-- NODE 2: AI Claude -->
  <g class="n2">
    <rect x="340" y="118" width="87" height="60" rx="8" fill="url(#ng0)" stroke="#B794F4" stroke-width="1.5" filter="url(#glow)"/>
    <text x="383" y="140" class="node-label">🤖 Claude AI</text>
    <text x="383" y="153" class="node-sub">Personalise</text>
    <text x="383" y="164" class="node-sub">Message</text>
  </g>

  <!-- NODE 3: WhatsApp -->
  <g class="n3">
    <rect x="487" y="118" width="87" height="60" rx="8" fill="url(#ng1)" stroke="#68D391" stroke-width="1.5" filter="url(#glow)"/>
    <text x="530" y="140" class="node-label">💬 WhatsApp</text>
    <text x="530" y="153" class="node-sub">Onboarding</text>
    <text x="530" y="164" class="node-sub">Message Sent</text>
  </g>

  <!-- NODE 4: Certificate -->
  <g class="n4">
    <rect x="634" y="118" width="86" height="60" rx="8" fill="url(#ng0)" stroke="#F6AD55" stroke-width="1.5" filter="url(#glow)"/>
    <text x="677" y="137" class="node-label">📜 PDF Gen</text>
    <text x="677" y="150" class="node-sub">Certificate</text>
    <text x="677" y="163" class="node-sub">+ Resend Email</text>
    <text x="677" y="174" class="node-sub">Delivered</text>
  </g>

  <!-- NODE 5: Done -->
  <g class="n5 done-mark">
    <circle cx="775" cy="148" r="14" fill="rgba(104,211,145,0.15)" stroke="#68D391" stroke-width="2" filter="url(#glow)"/>
    <text x="775" y="153" class="node-label" style="fill:#68D391;font-size:14px">✓</text>
  </g>

  <!-- ══════════ TRAVELLING PACKETS ══════════ -->
  <g class="pkt0" transform="translate(30,0)">
    <circle cx="103" cy="148" r="4" fill="#EA4B71" filter="url(#glow-strong)"/>
  </g>
  <g class="pkt1" transform="translate(193,0)">
    <circle cx="87" cy="148" r="4" fill="#EA4B71" filter="url(#glow-strong)"/>
  </g>
  <g class="pkt2" transform="translate(340,0)">
    <circle cx="87" cy="148" r="4" fill="#B794F4" filter="url(#glow-strong)"/>
  </g>
  <g class="pkt3" transform="translate(487,0)">
    <circle cx="87" cy="148" r="4" fill="#68D391" filter="url(#glow-strong)"/>
  </g>
  <g class="pkt4" transform="translate(634,0)">
    <circle cx="86" cy="148" r="4" fill="#F6AD55" filter="url(#glow-strong)"/>
  </g>

  <!-- ══════════ TIMER BAR ══════════ -->
  <rect x="200" y="215" width="400" height="1" fill="rgba(255,255,255,0.06)"/>

  <!-- Timer ticks -->
  <g>
    <text x="400" y="240" class="timer-lbl t0">⏱ 0.0s — Webhook received</text>
    <text x="400" y="240" class="timer-lbl t1">⏱ 0.7s — n8n routing...</text>
    <text x="400" y="240" class="timer-lbl t2">⏱ 1.4s — Claude generating message...</text>
    <text x="400" y="240" class="timer-lbl t3">⏱ 2.1s — WhatsApp sent ✓</text>
    <text x="400" y="240" class="timer-lbl t4">⏱ 3.5s — Certificate generated ✓</text>
    <text x="400" y="240" class="timer-lbl t5" style="fill:#68D391">⏱ 4.2s — Done. 3 hours of manual work saved.</text>
  </g>

  <!-- SAVED TIME LABEL -->
  <text x="400" y="266" class="saved-lbl">Without automation: 3 hrs manual work per registration</text>
  <text x="400" y="282" class="subtitle">With n8n: 4.2 seconds · zero human intervention · runs 24/7</text>

  <!-- BOTTOM DIVIDER -->
  <rect x="100" y="296" width="600" height="1" fill="rgba(234,75,113,0.15)"/>
  <text x="400" y="312" class="subtitle">vievek sharmaa · n8n Automation &amp; AI Builder · Jaipur, India</text>
</svg>

<!-- ═══════════════════════════════════════════════════════════ -->

# vievek sharmaa

### n8n Automation · AI Builder · Jaipur, Rajasthan 🇮🇳

[![Portfolio](https://img.shields.io/badge/Portfolio-0D0B12?style=for-the-badge&logo=firefox&logoColor=EA4B71)](https://your-portfolio-url.com)
[![Email](https://img.shields.io/badge/Gmail-EA4B71?style=for-the-badge&logo=gmail&logoColor=white)](mailto:vieveksharmaa@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-171515?style=for-the-badge&logo=github&logoColor=white)](https://github.com/vieveksharmaa)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR_LINKEDIN)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/917733977655)

</div>

---

## What I build

I build **n8n automation workflows** that eliminate manual work — triggered by payments, form submissions, or webhooks — and deliver personalised WhatsApp messages, emails, and PDFs without anyone touching them.

Combined with AI agents, full-stack Next.js apps, and RAG pipelines — I build complete products, not just isolated scripts.

---

## Selected Projects

### ⚡ [India Kids Talent Championship](https://your-portfolio-url.com/kidstar-case-study.html) &nbsp;·&nbsp; Client Work · In Production
> n8n · Razorpay · WhatsApp · Supabase · Next.js 15 · Resend

Full-stack nominations platform with **n8n-powered WhatsApp onboarding, payment recovery flows, and auto-certificate delivery**. 91.2% payment conversion. Built solo for Bharat Good Times — 5,000+ participant capacity.

`n8n` `Next.js 15` `Supabase` `Razorpay` `Resend` `WhatsApp`

---

### ⚡ [Vidhanm — Sacred Atelier](https://vidhanm.com) &nbsp;·&nbsp; [case study](https://your-portfolio-url.com/vidhanm-case-study.html)
> n8n · WooCommerce · Next.js 15 · Razorpay · Vercel

Premium spiritual e-commerce platform with **n8n post-purchase automation** — order confirmation, astrologer assignment, shipping triggers, customer WhatsApp. Headless WooCommerce + full brand system.

`n8n` `Next.js 15` `WooCommerce API` `Razorpay` `TypeScript` `Vercel`

---

### 🤖 [Job Search Co-Pilot](https://job-search-copilot-rho.vercel.app/) &nbsp;·&nbsp; [repo](https://github.com/vieveksharmaa/job-search-copilot)
> Vercel AI SDK · Next.js 14 · Anthropic Claude · TypeScript

5-step agentic AI pipeline — resume rewrite, cover letter, and interview questions in under 30 seconds. `streamText` + `toolChoice: 'required'` for reliable multi-tool streaming.

`Next.js 14` `Vercel AI SDK` `TypeScript` `Zod` `Claude Haiku`

---

### 🔍 [Multi-Source RAG with Citations](https://huggingface.co/spaces/vieveksharmaa/multi-source-rag) &nbsp;·&nbsp; [repo](https://github.com/vieveksharmaa/multi-source-rag)
> LangChain · LangGraph · Python · HuggingFace

RAG that ingests YouTube, PDFs, web pages, and GitHub repos — answers with exact citations including timestamps and page numbers. Every provider swappable via `.env`. Live on HuggingFace.

`Python` `LangChain` `LangGraph` `ChromaDB` `FastAPI` `Docker`

---

### 🛍️ [Product Description Generator](https://github.com/vieveksharmaa/product-description-generator)
> Ollama · Python · Local LLM · Open Source

AI e-commerce copy generator running entirely locally — no API keys, no cost. Desktop GUI + CLI, four tones, live streaming output.

`Python` `Ollama` `Tkinter` `Llama 3.2`

---

## n8n Automation Stack

```
Triggers      →  Razorpay Webhook · Form · HTTP · Schedule · WooCommerce
Actions       →  WhatsApp · Email (Resend) · PDF Generate · Supabase · Google Sheets
AI Inside n8n →  OpenAI · Claude · Switch Node · IF Node · AI Agent Node
Infra         →  Self-hosted n8n · Vercel · Docker · Cloudflare
```

---

## Full Stack

```
Automation    →  n8n  ★ primary
AI & Agents   →  Vercel AI SDK · LangChain · LangGraph · Anthropic · OpenAI · Ollama
Frontend      →  Next.js 15 · TypeScript · Tailwind CSS · React Server Components
Backend & DB  →  Supabase · FastAPI · WooCommerce REST API
Payments      →  Razorpay (webhooks + checkout)
Infra         →  Vercel · HuggingFace Spaces · Docker · Cloudflare
```

---

<div align="center">

### 🟢 Open to remote n8n automation & AI projects

**[vieveksharmaa@gmail.com](mailto:vieveksharmaa@gmail.com)** &nbsp;·&nbsp; **[WhatsApp](https://wa.me/917733977655)** &nbsp;·&nbsp; **[Portfolio](https://your-portfolio-url.com)**

*I build automations that run while you sleep.*

</div>

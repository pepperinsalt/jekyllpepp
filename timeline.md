---
layout: page
title: "Technical Evolution"
permalink: /timeline/
---

<style>
    .timeline-container { position: relative; max-width: 800px; margin: 40px auto; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: #334155; }
    .timeline-line { position: absolute; left: 50%; width: 2px; height: 100%; background: #cbd5e1; transform: translateX(-50%); }
    .epoch { position: relative; width: 45%; padding: 25px; background: #fff; border-radius: 12px; border: 1px solid #e2e8f0; margin-bottom: 40px; box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1); transition: transform 0.2s; }
    .epoch:hover { transform: translateY(-5px); }
    .epoch:nth-child(odd) { margin-left: 0; text-align: right; border-right: 4px solid #2563eb; }
    .epoch:nth-child(even) { margin-left: 55%; text-align: left; border-left: 4px solid #2563eb; }
    .epoch-title { color: #1e293b; font-weight: 800; font-size: 1.4rem; margin-bottom: 8px; }
    .epoch-date { font-weight: 600; color: #2563eb; font-size: 0.9rem; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 10px; display: block; }
    .skills-box { margin-top: 15px; }
    .skill-tag { display: inline-block; background: #f1f5f9; color: #475569; padding: 4px 12px; border-radius: 20px; font-size: 0.8rem; margin: 3px; border: 1px solid #e2e8f0; font-weight: 500; }
    .marker { position: absolute; top: 30px; left: 50%; width: 16px; height: 16px; background: #2563eb; border: 4px solid #fff; border-radius: 50%; transform: translateX(-50%); z-index: 2; box-shadow: 0 0 0 2px #cbd5e1; }
    @media (max-width: 768px) {
        .timeline-line { left: 20px; }
        .epoch { width: 85%; margin-left: 45px !important; text-align: left !important; border-right: none !important; border-left: 4px solid #2563eb !important; }
        .marker { left: 20px; }
    }
</style>

<div class="timeline-container">
    <div class="timeline-line"></div>

    <div class="epoch">
        <div class="marker"></div>
        <span class="epoch-date">2015 - 2018</span>
        <div class="epoch-title">The Web Foundation Epoch</div>
        <p>Focused on architectural delivery for WordPress and high-traffic WooCommerce environments, specializing in front-end performance and custom CMS logic.</p>
        <div class="skills-box">
            <span class="skill-tag">WordPress</span> <span class="skill-tag">PHP</span> <span class="skill-tag">WooCommerce</span> <span class="skill-tag">UI/UX</span>
        </div>
    </div>

    <div class="epoch">
        <div class="marker"></div>
        <span class="epoch-date">2018 - 2021</span>
        <div class="epoch-title">Infrastructure & Physical Systems</div>
        <p>Transitioned into the physical layer of tech, managing data cabling infrastructure, enterprise network hardware, and macOS/Linux fleet management.</p>
        <div class="skills-box">
            <span class="skill-tag">Data Cabling</span> <span class="skill-tag">Network Engineering</span> <span class="skill-tag">Linux Administration</span>
        </div>
    </div>

    <div class="epoch">
        <div class="marker"></div>
        <span class="epoch-date">2021 - 2024</span>
        <div class="epoch-title">Automation & Advanced Scripting</div>
        <p>Engineering specialized automation tools, including Chrome extensions for labor platforms and system-level scripting for mobile device management.</p>
        <div class="skills-box">
            <span class="skill-tag">Chrome Extensions</span> <span class="skill-tag">ADB/Fastboot</span> <span class="skill-tag">Python</span> <span class="skill-tag">Automation</span>
        </div>
    </div>

    <div class="epoch">
        <div class="marker"></div>
        <span class="epoch-date">2024 - Present</span>
        <div class="epoch-title">Enterprise Architecture Epoch</div>
        <p>Leading large-scale migrations from legacy systems (SharePoint) to modern MVC stacks, and building high-performance e-commerce monitoring engines.</p>
        <div class="skills-box">
            <span class="skill-tag">Laravel</span> <span class="skill-tag">MVC Architecture</span> <span class="skill-tag">SQL Design</span> <span class="skill-tag">Jekyll</span>
        </div>
    </div>
</div>

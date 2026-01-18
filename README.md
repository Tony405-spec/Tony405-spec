<svg width="800" height="600" xmlns="http://www.w3.org/2000/svg" style="background: linear-gradient(45deg, #0a0a0a, #1a1d2c); font-family: 'Courier New', monospace;">

  <!-- Background Grid Pattern -->
  <defs>
    <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
      <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#333" stroke-width="1" opacity="0.3"/>
    </pattern>
    
    <!-- Robot Body Gradient -->
    <linearGradient id="robotGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#4dabf7;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#2a2d43;stop-opacity:1" />
    </linearGradient>
    
    <!-- Glowing Effect -->
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- Grid Background -->
  <rect width="100%" height="100%" fill="url(#grid)"/>
  
  <!-- Data Stream Lines -->
  <path d="M 0 100 Q 200 80 400 120 T 800 100" stroke="#4dabf7" stroke-width="2" fill="none" opacity="0.5">
    <animate attributeName="d" dur="4s" repeatCount="indefinite"
      values="M 0 100 Q 200 80 400 120 T 800 100;
              M 0 120 Q 200 100 400 140 T 800 120;
              M 0 100 Q 200 80 400 120 T 800 100"/>
  </path>
  
  <path d="M 0 150 Q 200 130 400 170 T 800 150" stroke="#ff3333" stroke-width="2" fill="none" opacity="0.5">
    <animate attributeName="d" dur="3s" repeatCount="indefinite"
      values="M 0 150 Q 200 130 400 170 T 800 150;
              M 0 170 Q 200 150 400 190 T 800 170;
              M 0 150 Q 200 130 400 170 T 800 150"/>
  </path>
  
  <!-- Walking Robot -->
  <g id="robot" transform="translate(200, 300)">
    
    <!-- Body -->
    <rect x="-30" y="-50" width="60" height="100" rx="10" fill="url(#robotGradient)" stroke="#4dabf7" stroke-width="3" filter="url(#glow)"/>
    
    <!-- Head -->
    <circle cx="0" cy="-80" r="25" fill="url(#robotGradient)" stroke="#4dabf7" stroke-width="3" filter="url(#glow)"/>
    
    <!-- Antenna -->
    <line x1="0" y1="-105" x2="0" y2="-120" stroke="#ff3333" stroke-width="2">
      <animate attributeName="y2" dur="1s" values="-120;-115;-120" repeatCount="indefinite"/>
    </line>
    <circle cx="0" cy="-120" r="3" fill="#ff3333">
      <animate attributeName="r" dur="1s" values="3;4;3" repeatCount="indefinite"/>
    </circle>
    
    <!-- Eyes (Data Display) -->
    <g>
      <rect x="-8" y="-85" width="16" height="10" rx="2" fill="#0a0a0a"/>
      <!-- Moving data -->
      <text x="0" y="-78" text-anchor="middle" fill="#00FF41" font-size="8" font-family="'Courier New', monospace">
        <animate attributeName="y" dur="2s" values="-78;-77;-78" repeatCount="indefinite"/>
        1010
      </text>
    </g>
    
    <!-- Arms -->
    <g id="leftArm">
      <line x1="-30" y1="-40" x2="-60" y2="-10" stroke="#4dabf7" stroke-width="4">
        <animate attributeName="x2" dur="0.8s" values="-60;-65;-60" repeatCount="indefinite"/>
      </line>
      <circle cx="-60" cy="-10" r="6" fill="#4dabf7">
        <animate attributeName="cy" dur="0.8s" values="-10;-15;-10" repeatCount="indefinite"/>
      </circle>
    </g>
    
    <g id="rightArm">
      <line x1="30" y1="-40" x2="60" y2="-10" stroke="#4dabf7" stroke-width="4">
        <animate attributeName="x2" dur="0.8s" values="60;65;60" repeatCount="indefinite"/>
      </line>
      <circle cx="60" cy="-10" r="6" fill="#4dabf7">
        <animate attributeName="cy" dur="0.8s" values="-10;-15;-10" repeatCount="indefinite"/>
      </circle>
    </g>
    
    <!-- Legs -->
    <g id="leftLeg">
      <line x1="-15" y1="50" x2="-20" y2="90" stroke="#4dabf7" stroke-width="4">
        <animate attributeName="y2" dur="0.8s" values="90;100;90" repeatCount="indefinite"/>
      </line>
      <rect x="-25" y="90" width="10" height="15" rx="2" fill="#4dabf7">
        <animate attributeName="y" dur="0.8s" values="90;95;90" repeatCount="indefinite"/>
      </rect>
    </g>
    
    <g id="rightLeg">
      <line x1="15" y1="50" x2="10" y2="80" stroke="#4dabf7" stroke-width="4">
        <animate attributeName="y2" dur="0.8s" values="80;90;80" repeatCount="indefinite"/>
        <animate attributeName="x2" dur="0.8s" values="10;5;10" repeatCount="indefinite"/>
      </line>
      <rect x="5" y="80" width="10" height="15" rx="2" fill="#4dabf7">
        <animate attributeName="y" dur="0.8s" values="80;85;80" repeatCount="indefinite"/>
      </rect>
    </g>
    
    <!-- Walking Animation for whole robot -->
    <animateTransform 
      attributeName="transform" 
      type="translate" 
      values="200,300; 600,300; 200,300" 
      dur="8s" 
      repeatCount="indefinite"/>
    
  </g>
  
  <!-- Data Science Student Info Box -->
  <g transform="translate(50, 450)">
    
    <!-- Terminal Box -->
    <rect x="0" y="0" width="700" height="120" rx="10" fill="#1a1d2c" stroke="#4dabf7" stroke-width="2" opacity="0.9"/>
    
    <!-- Terminal Header -->
    <rect x="0" y="0" width="700" height="25" rx="10 10 0 0" fill="#2a2d43"/>
    <circle cx="15" cy="12" r="5" fill="#ff3333"/>
    <circle cx="35" cy="12" r="5" fill="#FFA500"/>
    <circle cx="55" cy="12" r="5" fill="#00FF41"/>
    <text x="80" y="17" fill="#ffffff" font-size="12" font-weight="bold">Data Science Terminal v2.0</text>
    
    <!-- Terminal Content -->
    <g font-family="'Courier New', monospace" font-size="14" fill="#ffffff">
      
      <!-- First line with cursor animation -->
      <text x="20" y="50">
        <tspan fill="#00FF41">>>> </tspan>
        <tspan fill="#ffffff">Initializing Student Profile...</tspan>
        <tspan fill="#00FF41">█</tspan>
        <animate attributeName="opacity" dur="1s" values="1;0;1" repeatCount="indefinite"/>
      </text>
      
      <!-- Student Info -->
      <text x="20" y="70">
        <tspan fill="#00FF41">>>> </tspan>
        <tspan fill="#ffffff">Name: </tspan>
        <tspan fill="#4dabf7" font-weight="bold">Tony Kenga</tspan>
      </text>
      
      <text x="20" y="90">
        <tspan fill="#00FF41">>>> </tspan>
        <tspan fill="#ffffff">Role: </tspan>
        <tspan fill="#4dabf7">Data Science Student & AI Researcher</tspan>
      </text>
      
      <text x="20" y="110">
        <tspan fill="#00FF41">>>> </tspan>
        <tspan fill="#ffffff">Focus: </tspan>
        <tspan fill="#4dabf7">Machine Learning • Neural Networks • Data Engineering</tspan>
      </text>
      
      <text x="20" y="130">
        <tspan fill="#00FF41">>>> </tspan>
        <tspan fill="#ffffff">Mission: </tspan>
        <tspan fill="#ff3333">Transforming data into intelligent solutions</tspan>
      </text>
      
    </g>
    
  </g>
  
  <!-- Skills Progress Bars -->
  <g transform="translate(50, 580)">
    <text x="0" y="-10" fill="#ffffff" font-size="16" font-weight="bold">Core Competencies:</text>
    
    <!-- Python -->
    <text x="0" y="15" fill="#4dabf7" font-size="12">Python</text>
    <rect x="80" y="5" width="200" height="12" rx="6" fill="#333"/>
    <rect x="80" y="5" width="180" height="12" rx="6" fill="#3776AB">
      <animate attributeName="width" from="0" to="180" dur="1s" fill="freeze"/>
    </rect>
    <text x="290" y="15" fill="#00FF41" font-size="12">90%</text>
    
    <!-- Machine Learning -->
    <text x="0" y="35" fill="#4dabf7" font-size="12">Machine Learning</text>
    <rect x="80" y="25" width="200" height="12" rx="6" fill="#333"/>
    <rect x="80" y="25" width="160" height="12" rx="6" fill="#FF6F00">
      <animate attributeName="width" from="0" to="160" begin="0.3s" dur="1s" fill="freeze"/>
    </rect>
    <text x="290" y="35" fill="#00FF41" font-size="12">80%</text>
    
    <!-- Data Analysis -->
    <text x="0" y="55" fill="#4dabf7" font-size="12">Data Analysis</text>
    <rect x="80" y="45" width="200" height="12" rx="6" fill="#333"/>
    <rect x="80" y="45" width="170" height="12" rx="6" fill="#00FF41">
      <animate attributeName="width" from="0" to="170" begin="0.6s" dur="1s" fill="freeze"/>
    </rect>
    <text x="290" y="55" fill="#00FF41" font-size="12">85%</text>
    
  </g>
  
  <!-- Binary Rain Effect -->
  <g id="binaryRain" opacity="0.3">
    <text x="50" y="20" fill="#4dabf7" font-size="10">1010</text>
    <text x="150" y="40" fill="#4dabf7" font-size="10">1101</text>
    <text x="250" y="60" fill="#4dabf7" font-size="10">0010</text>
    <text x="350" y="80" fill="#4dabf7" font-size="10">1110</text>
    <text x="450" y="100" fill="#4dabf7" font-size="10">0101</text>
    <text x="550" y="120" fill="#4dabf7" font-size="10">1011</text>
    <text x="650" y="140" fill="#4dabf7" font-size="10">0110</text>
    <text x="750" y="160" fill="#4dabf7" font-size="10">1001</text>
    
    <!-- Animate binary rain falling -->
    <animateTransform attributeName="transform" type="translate" values="0,0; 0,20" dur="2s" repeatCount="indefinite"/>
  </g>
  
  <!-- Title -->
  <text x="400" y="30" text-anchor="middle" fill="#4dabf7" font-size="28" font-weight="bold">
    Data Science Learning Machine
    <animate attributeName="opacity" values="0.7;1;0.7" dur="2s" repeatCount="indefinite"/>
  </text>
  
  <!-- Subtitle -->
  <text x="400" y="60" text-anchor="middle" fill="#ffffff" font-size="16" font-style="italic">
    Walking through data, one algorithm at a time
  </text>

</svg>

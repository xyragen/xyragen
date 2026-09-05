<svg xmlns="http://www.w3.org/2000/svg"
     width="760"
     height="430"
     viewBox="0 0 760 430">

  <style>
    .terminal {
      fill: #000;
      stroke: #222;
      stroke-width: 2;
    }

    .prompt,
    .command,
    .error {
      font-family: "Courier New", monospace;
      font-size: 20px;
      dominant-baseline: hanging;
      letter-spacing: 0;
    }

    .prompt,
    .command,
    .error,
    .cursor {
      fill: #fff;
    }

    /* Type: rm -rf / */
    #command1 {
      clip-path: inset(0 100% 0 0);
      animation: typeCommand1 14s steps(8, end) infinite;
    }

    /* Type: sudo rm -rf / */
    #command2 {
      clip-path: inset(0 100% 0 0);
      animation: typeCommand2 14s steps(13, end) infinite;
    }

    /* First cursor follows each typed character */
    #cursor1 {
      animation:
        cursor1Position 14s steps(1, end) infinite,
        cursor1Visibility 14s steps(1, end) infinite,
        blink 0.8s steps(1) infinite;
    }

    /* Second cursor follows each typed character */
    #cursor2 {
      animation:
        cursor2Position 14s steps(1, end) infinite,
        cursor2Visibility 14s steps(1, end) infinite,
        blink 0.8s steps(1) infinite;
    }

    /* Error appears after the first command */
    #error {
      opacity: 0;
      animation: showError 14s steps(1, end) infinite;
    }

    /* First command typing:
       0.8s–2.8s
       erase at 5.5s–6.3s */
    @keyframes typeCommand1 {
      0%, 5.7% {
        clip-path: inset(0 100% 0 0);
      }

      20% {
        clip-path: inset(0 0 0 0);
      }

      39% {
        clip-path: inset(0 0 0 0);
      }

      45% {
        clip-path: inset(0 100% 0 0);
      }

      100% {
        clip-path: inset(0 100% 0 0);
      }
    }

    /* Second command typing:
       7.2s–10.5s
       erase at 12.2s–13.4s */
    @keyframes typeCommand2 {
      0%, 51% {
        clip-path: inset(0 100% 0 0);
      }

      75% {
        clip-path: inset(0 0 0 0);
      }

      87% {
        clip-path: inset(0 0 0 0);
      }

      96% {
        clip-path: inset(0 100% 0 0);
      }

      100% {
        clip-path: inset(0 100% 0 0);
      }
    }

    /* Cursor 1 moves from after the prompt,
       through each character of "rm -rf /" */
    @keyframes cursor1Position {
      0%, 6%   { x: 308px; }
      8%       { x: 320px; }
      10%      { x: 332px; }
      12%      { x: 344px; }
      14%      { x: 356px; }
      16%      { x: 368px; }
      18%      { x: 380px; }
      20%      { x: 392px; }
      22%      { x: 404px; }
      45%, 100% { x: 308px; }
    }

    @keyframes cursor1Visibility {
      0%, 45% { opacity: 1; }
      46%, 100% { opacity: 0; }
    }

    /* Cursor 2 moves through "sudo rm -rf /" */
    @keyframes cursor2Position {
      0%, 52% { x: 308px; }
      54% { x: 320px; }
      56% { x: 332px; }
      58% { x: 344px; }
      60% { x: 356px; }
      62% { x: 368px; }
      64% { x: 380px; }
      66% { x: 392px; }
      68% { x: 404px; }
      70% { x: 416px; }
      72% { x: 428px; }
      74% { x: 440px; }
      76% { x: 452px; }
      78% { x: 464px; }
      96%, 100% { x: 308px; }
    }

    @keyframes cursor2Visibility {
      0%, 50% { opacity: 0; }
      51%, 96% { opacity: 1; }
      97%, 100% { opacity: 0; }
    }

    @keyframes showError {
      0%, 27% {
        opacity: 0;
      }

      28%, 43% {
        opacity: 1;
      }

      44%, 100% {
        opacity: 0;
      }
    }

    @keyframes blink {
      0%, 49% {
        opacity: 1;
      }

      50%, 100% {
        opacity: 0;
      }
    }
  </style>

  <!-- Black background -->
  <rect width="760" height="430" fill="#000"/>

  <!-- Minimal rounded terminal -->
  <rect
    class="terminal"
    x="30"
    y="30"
    width="700"
    height="370"
    rx="64"
    ry="64"
  />

  <!-- First prompt -->
  <text class="prompt" x="55" y="120">
    xyragen@archlinux:~$
  </text>

  <text id="command1" class="command" x="308" y="120">
    rm -rf /
  </text>

  <rect
    id="cursor1"
    class="cursor"
    x="308"
    y="122"
    width="12"
    height="22"
  />

  <!-- Error -->
  <text id="error" class="error" x="55" y="180">
    error: permission denied
  </text>

  <!-- Second prompt -->
  <text class="prompt" x="55" y="250">
    xyragen@archlinux:~$
  </text>

  <text id="command2" class="command" x="308" y="250">
    sudo rm -rf /
  </text>

  <rect
    id="cursor2"
    class="cursor"
    x="308"
    y="252"
    width="12"
    height="22"
  />
</svg>

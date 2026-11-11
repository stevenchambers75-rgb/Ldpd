<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
  <title>LSPD Mobile Data Terminal - FiveM LSPDFR Edition</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Chakra+Petch:ital,wght@0,400;0,600;0,700;1,700&family=JetBrains+Mono:wght@400;600;700;800&family=Teko:wght@600;700&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            gtadark: '#070a0e',
            gtaslate: '#0f141c',
            gtacard: '#141b24',
            gtaglass: 'rgba(16, 23, 34, 0.85)',
            lspdblue: '#1b64da',
            lspdcyan: '#00d2ff',
            lspdgold: '#e6a100',
            lspdred: '#ff2a2a',
            matrixgreen: '#10b981'
          },
          fontFamily: {
            pricedown: ['Teko', 'Impact', 'sans-serif'],
            tactical: ['Chakra Petch', 'sans-serif'],
            mono: ['JetBrains Mono', 'monospace']
          }
        }
      }
    }
  </script>
  <style>
    .crt-scanlines {
      background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.35) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.03), rgba(0, 255, 0, 0.01), rgba(0, 0, 255, 0.03));
      background-size: 100% 3px, 6px 100%;
      pointer-events: none;
    }
    .neon-border-blue {
      box-shadow: 0 0 15px rgba(27, 100, 218, 0.35), inset 0 0 10px rgba(0, 210, 255, 0.1);
    }
    .neon-border-red {
      box-shadow: 0 0 20px rgba(255, 42, 42, 0.6), inset 0 0 15px rgba(255, 42, 42, 0.2);
    }
    .wanted-star {
      transition: all 0.25s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    .wanted-star.active {
      color: #ffcc00;
      filter: drop-shadow(0 0 8px rgba(255, 204, 0, 0.9));
      transform: scale(1.15);
      animation: starFlicker 1.8s infinite alternate;
    }
    @keyframes starFlicker {
      0% { opacity: 0.88; transform: scale(1.12); }
      100% { opacity: 1; transform: scale(1.22); }
    }
    @keyframes panicPulse {
      0%, 100% { background-color: rgba(255, 42, 42, 0.04); }
      50% { background-color: rgba(255, 42, 42, 0.25); }
    }
    .panic-active {
      animation: panicPulse 0.45s infinite !important;
      border-color: #ff2a2a !important;
    }
    .phone-slide-enter {
      transform: translateY(110%);
      transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1);
    }
    .phone-slide-enter.active {
      transform: translateY(0);
    }
    .phone-shadow {
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.8), 0 0 20px rgba(0, 210, 255, 0.25);
    }
    ::-webkit-scrollbar { width: 4px; height: 4px; }
    ::-webkit-scrollbar-track { background: #070a0e; }
    ::-webkit-scrollbar-thumb { background: #223042; border-radius: 2px; }
    ::-webkit-scrollbar-thumb:hover { background: #00d2ff; }
  </style>
</head>
<body class="bg-gtadark text-slate-100 font-tactical antialiased select-none min-h-screen flex flex-col justify-between overflow-x-hidden pb-16">
  
  <div class="fixed inset-0 crt-scanlines z-50 pointer-events-none"></div>

  <header class="sticky top-0 z-40 bg-gtaslate/95 backdrop-blur border-b border-cyan-900/50 px-3 py-2">
    <div class="flex items-center justify-between">
      <div class="flex items-center gap-2">
        <div class="relative w-8 h-8 rounded-full bg-gradient-to-tr from-amber-600 to-yellow-300 p-0.5 shadow-md flex items-center justify-center">
          <svg class="w-6 h-6 text-slate-900 drop-shadow" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 2L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-3zm0 4a3 3 0 110 6 3 3 0 010-6zm5 11.2c-1.3-1.64-3.32-2.7-5-2.7s-3.7 1.06-5 2.7c1.47 1.48 3.53 2.5 5 2.5s3.53-1.02 5-2.5z"/>
          </svg>
        </div>
        <div>
          <div class="flex items-center gap-1.5 leading-none">
            <s
... 

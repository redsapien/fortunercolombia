<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport"
        content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes, viewport-fit=cover">
    <meta name="theme-color" content="#0A2A4A">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>Fortuner ERP | Software Empresarial</title>

    
    <link
        href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&family=Inter:wght@300;400;700;900&family=Anton&display=swap"
        rel="stylesheet">

    <!-- Favicon Generado en Código (Isotipo 3 Flechas) -->
    <link rel="icon"
        href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Cg transform='translate(50, 50)'%3E%3Cpath d='M0,-30 L15,10 L-15,10 Z' fill='%23F5A623' transform='rotate(0)' /%3E%3Cpath d='M0,-30 L15,10 L-15,10 Z' fill='%230066FF' transform='rotate(120)' /%3E%3Cpath d='M0,-30 L15,10 L-15,10 Z' fill='%232ECC71' transform='rotate(240)' /%3E%3C/g%3E%3C/svg%3E">
    <link rel="apple-touch-icon" href="Imagenes/Logo-Fortuner.webp">

    <style>
        /* ---------------------------------------------
           1. RESET Y VARIABLES (COLORES FORTUNER)
        --------------------------------------------- */
        :root {
            --f-blue-dark: #0A2A4A;
            --f-blue-electric: #0066FF;
            --f-gold: #F5A623;
            --f-green: #2ECC71;
            --f-white: #FFFFFF;
            --f-gray-light: #E0E0E0;
            --f-gray-dark: #1A1A1A;
            --f-black: #0D0D0D;

            --font-main: 'Inter', sans-serif;
            --font-title: 'Anton', sans-serif;
            --font-mono: 'Orbitron', sans-serif;

            --section-padding-desktop: 120px 5%;
            --card-padding: 40px 35px;
            --gap-lg: 40px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body,
        html {
            height: 100%;
            background-color: var(--f-black);
            font-family: var(--font-main);
            color: var(--f-white);
            overflow-x: hidden;
            scrollbar-width: none;
            scroll-behavior: smooth;
        }

        body::-webkit-scrollbar {
            display: none;
        }

        /* ---------------------------------------------
           2. PRELOADER (Ingresando al sistema...)
        --------------------------------------------- */
        #preloader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--f-black);
            z-index: 10000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: opacity 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            pointer-events: none;
        }

        .loader-wrap {
            text-align: center;
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .fortuner-loader-logo {
            position: relative;
            width: 150px;
            height: 150px;
            margin-bottom: 30px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .fortuner-loader-logo .arc {
            position: absolute;
            border-radius: 50%;
            border: 4px solid transparent;
        }

        /* Amarillo */
        .fortuner-loader-logo .arc1 {
            width: 100%;
            height: 100%;
            border-top-color: var(--f-gold);
            border-right-color: var(--f-gold);
            animation: spinGear 2s linear infinite;
        }

        /* Azul */
        .fortuner-loader-logo .arc2 {
            width: 70%;
            height: 70%;
            border-bottom-color: var(--f-blue-electric);
            border-left-color: var(--f-blue-electric);
            animation: spinGear 2s linear infinite reverse;
        }

        /* Verde */
        .fortuner-loader-logo .arc3 {
            width: 40%;
            height: 40%;
            border-top-color: var(--f-green);
            border-left-color: var(--f-blue-electric);
            animation: spinGear 1.5s linear infinite;
        }

        .fortuner-loader-logo .center-core {
            position: absolute;
            width: 20px;
            height: 20px;
            background: var(--f-blue-electric);
            border-radius: 50%;
            box-shadow: 0 0 30px var(--f-blue-electric);
            z-index: 2;
        }

        @keyframes spinGear {
            0% {
                transform: rotate(0deg);
            }

            100% {
                transform: rotate(360deg);
            }
        }

        .loader-text {
            font-family: var(--font-mono);
            font-size: 14px;
            letter-spacing: 4px;
            text-transform: uppercase;
            color: var(--f-blue-electric);
            animation: pulseText 1.5s infinite;
            font-weight: 900;
            margin-top: 20px;
        }

        .loader-text span {
            color: var(--f-gold);
        }

        @keyframes pulseText {

            0%,
            100% {
                opacity: 0.5;
            }

            50% {
                opacity: 1;
            }
        }

        .loader-bar {
            width: 200px;
            height: 3px;
            background: #1a1a1a;
            border-radius: 3px;
            margin-top: 30px;
            overflow: hidden;
        }

        .loader-bar-fill {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, var(--f-blue-electric), var(--f-gold));
            border-radius: 3px;
            animation: fillBar 2s ease-in-out forwards;
        }

        @keyframes fillBar {
            0% {
                width: 0%;
            }

            100% {
                width: 100%;
            }
        }

        /* ---------------------------------------------
           3. ANIMACIONES GLOBALES 3D
        --------------------------------------------- */
        @keyframes techPulse {
            0% {
                opacity: 0.3;
                transform: scale(0.95);
            }

            50% {
                opacity: 0.8;
                transform: scale(1.05);
            }

            100% {
                opacity: 0.3;
                transform: scale(0.95);
            }
        }

        @keyframes floatBackground {
            0% {
                transform: translate(0, 0) rotate(0deg);
            }

            100% {
                transform: translate(-50px, -30px) rotate(5deg);
            }
        }

        @keyframes floatParticle {
            0% {
                transform: translate(0, 0) scale(1);
                opacity: 0.2;
            }

            100% {
                transform: translate(30px, -40px) scale(2);
                opacity: 0.6;
            }
        }

        @keyframes unlockChest {
            0% {
                transform: rotate(-15deg) scale(0.9);
                opacity: 0.7;
            }

            50% {
                transform: rotate(5deg) scale(1.1);
                opacity: 1;
            }

            100% {
                transform: rotate(0deg) scale(1);
                opacity: 1;
            }
        }

        @keyframes energyFlow {
            0% {
                background-position: -200% 0;
            }

            100% {
                background-position: 200% 0;
            }
        }

        /* ---------------------------------------------
           4. BARRA DE PODER TECNOLÓGICA
        --------------------------------------------- */
        .power-bar {
            position: fixed;
            top: 0;
            width: 100%;
            height: 4px;
            z-index: 100;
            background: rgba(10, 42, 74, 0.6);
            backdrop-filter: blur(4px);
            display: flex;
            align-items: center;
            overflow: hidden;
            border-bottom: 1px solid rgba(0, 102, 255, 0.2);
        }

        .power-energy {
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, var(--f-blue-electric), var(--f-gold), var(--f-blue-electric), transparent);
            background-size: 200% 100%;
            animation: energyFlow 3s linear infinite;
        }

        /* ---------------------------------------------
           5. HERO (Malla Cerebral Avanzada)
        --------------------------------------------- */
        .main-engine {
            position: relative;
            width: 100%;
            height: 100vh;
            height: 100dvh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            text-align: center;
            overflow: hidden;
            background: var(--f-black);
        }

        .tech-brain-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .tech-brain-bg .neuron {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(0, 102, 255, 0.15) 0%, transparent 70%);
            animation: techPulse 4s infinite ease-in-out;
        }

        .tech-brain-bg .neuron:nth-child(1) {
            width: 300px;
            height: 300px;
            top: -50px;
            left: -80px;
            animation-delay: 0s;
        }

        .tech-brain-bg .neuron:nth-child(2) {
            width: 400px;
            height: 400px;
            bottom: -100px;
            right: -100px;
            animation-delay: 1s;
        }

        .tech-brain-bg .neuron:nth-child(3) {
            width: 200px;
            height: 200px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation-delay: 2s;
        }

        .tech-brain-bg .circuit-line {
            position: absolute;
            background: linear-gradient(90deg, transparent, rgba(0, 102, 255, 0.08), transparent);
            height: 1px;
            width: 70%;
            top: 30%;
            left: 15%;
            transform: rotate(-15deg);
            animation: floatBackground 8s infinite alternate;
        }

        .tech-brain-bg .circuit-line:nth-child(4) {
            top: 60%;
            left: 10%;
            width: 60%;
            transform: rotate(25deg);
            animation-delay: 2s;
        }

        .tech-brain-bg .circuit-line:nth-child(5) {
            top: 45%;
            left: 5%;
            width: 50%;
            transform: rotate(5deg);
            animation-delay: 4s;
        }

        .tech-brain-bg .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: var(--f-blue-electric);
            border-radius: 50%;
            opacity: 0.3;
            animation: floatParticle 10s infinite alternate;
        }

        .tech-brain-bg .particle:nth-child(6) {
            top: 20%;
            left: 10%;
            animation-duration: 8s;
        }

        .tech-brain-bg .particle:nth-child(7) {
            top: 70%;
            left: 80%;
            animation-duration: 12s;
            animation-delay: 2s;
        }

        .content-box {
            position: relative;
            z-index: 10;
            max-width: 850px;
        }

        .headline {
            font-family: var(--font-title);
            font-size: clamp(2.8rem, 8vw, 5rem);
            line-height: 1.2;
            text-transform: uppercase;
            margin-bottom: 25px;
            color: var(--f-white);
            letter-spacing: 1px;
        }

        .headline span {
            color: var(--f-blue-electric);
            position: relative;
        }

        .headline span::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--f-blue-electric), var(--f-gold));
            border-radius: 3px;
        }

        .paragraph {
            font-size: clamp(1rem, 2.5vw, 1.2rem);
            line-height: 1.7;
            color: var(--f-gray-light);
            max-width: 600px;
            margin: 0 auto 45px;
            font-weight: 400;
            background: rgba(10, 42, 74, 0.5);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(0, 102, 255, 0.15);
            border-radius: 16px;
            padding: 24px 32px;
            box-shadow: 0 25px 40px rgba(0, 0, 0, 0.6);
        }

        .paragraph strong {
            color: var(--f-gold);
            font-weight: 700;
        }

        .cta-premium {
            position: relative;
            display: inline-block;
            padding: 22px 60px;
            background: transparent;
            border: 2px solid var(--f-blue-electric);
            color: var(--f-white);
            font-family: var(--font-mono);
            font-weight: 900;
            font-size: 1.1rem;
            text-decoration: none;
            border-radius: 8px;
            overflow: hidden;
            transition: all 0.4s ease;
            cursor: pointer;
            box-shadow: 0 0 30px rgba(0, 102, 255, 0.15);
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .cta-premium:hover {
            background: var(--f-blue-electric);
            border-color: var(--f-blue-electric);
            box-shadow: 0 0 50px rgba(0, 102, 255, 0.4);
            transform: translateY(-3px);
        }

        .cta-premium::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.15), transparent);
            transition: 0.6s;
        }

        .cta-premium:hover::before {
            left: 100%;
        }

        /* ---------------------------------------------
           6. SECCIÓN 2: CATÁLOGO MÓDULOS (Más ancho en móvil)
        --------------------------------------------- */
        .f-modules-section {
            background: var(--f-black);
            padding: var(--section-padding-desktop);
            position: relative;
            overflow: hidden;
        }

        .f-modules-section .bg-tech-pattern {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: radial-gradient(circle at 20% 50%, rgba(0, 102, 255, 0.05) 0%, transparent 50%), radial-gradient(circle at 80% 20%, rgba(245, 166, 35, 0.03) 0%, transparent 40%);
            pointer-events: none;
            z-index: 0;
        }

        .modules-container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
        }

        .modules-title {
            font-family: var(--font-title);
            font-size: clamp(2.2rem, 6vw, 3.8rem);
            text-transform: uppercase;
            text-align: center;
            margin-bottom: 70px;
            color: var(--f-white);
            letter-spacing: 2px;
        }

        .modules-title span {
            color: var(--f-blue-electric);
        }

        .modules-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: var(--gap-lg);
        }

        .module-card {
            background: rgba(10, 42, 74, 0.3);
            border: 1px solid rgba(0, 102, 255, 0.12);
            border-radius: 20px;
            padding: var(--card-padding);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            backdrop-filter: blur(4px);
            display: flex;
            flex-direction: column;
        }

        .module-card:hover {
            border-color: var(--f-blue-electric);
            transform: translateY(-8px);
            box-shadow: 0 20px 50px rgba(0, 102, 255, 0.1);
            background: rgba(10, 42, 74, 0.5);
        }

        .module-img-wrapper {
            width: 100%;
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 20px;
            border: 1px solid rgba(0, 102, 255, 0.1);
            cursor: pointer;
            transition: 0.3s;
            position: relative;
        }

        .module-img-wrapper img {
            width: 100%;
            height: auto;
            display: block;
            transition: 0.3s;
        }

        .module-img-wrapper:hover img {
            transform: scale(1.02);
        }

        .module-card h3 {
            font-family: var(--font-mono);
            font-size: 1.1rem;
            color: var(--f-blue-electric);
            margin-bottom: 12px;
            letter-spacing: 1px;
        }

        .module-card p {
            color: var(--f-gray-light);
            font-size: 0.95rem;
            line-height: 1.7;
            margin-bottom: 20px;
            flex: 1;
        }

        .module-card .btn-module {
            display: inline-block;
            padding: 10px 25px;
            background: transparent;
            border: 1px solid var(--f-blue-electric);
            color: var(--f-white);
            font-family: var(--font-mono);
            font-size: 0.7rem;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            text-align: center;
            letter-spacing: 1px;
            align-self: flex-start;
        }

        .module-card .btn-module:hover {
            background: var(--f-blue-electric);
            box-shadow: 0 0 25px rgba(0, 102, 255, 0.3);
        }

        /* ---------------------------------------------
           7. SECCIÓN 3: PANEL DE CONTROL
        --------------------------------------------- */
        .f-control-section {
            background: var(--f-black);
            padding: var(--section-padding-desktop);
            position: relative;
            overflow: hidden;
            border-top: 1px solid rgba(0, 102, 255, 0.05);
            border-bottom: 1px solid rgba(0, 102, 255, 0.05);
        }

        .control-container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .control-text h2 {
            font-family: var(--font-title);
            font-size: clamp(2.5rem, 5vw, 4rem);
            text-transform: uppercase;
            line-height: 1.2;
            margin-bottom: 25px;
            color: var(--f-white);
        }

        .control-text h2 .highlight {
            color: var(--f-blue-electric);
            position: relative;
        }

        .control-text h2 .highlight::after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--f-gold);
            border-radius: 3px;
        }

        .control-text p {
            color: var(--f-gray-light);
            font-size: 1.05rem;
            line-height: 1.8;
            margin-bottom: 30px;
        }

        .control-text .feature-list {
            list-style: none;
            padding: 0;
        }

        .control-text .feature-list li {
            padding: 8px 0;
            color: var(--f-gray-light);
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 0.95rem;
        }

        .control-text .feature-list li::before {
            content: '▸';
            color: var(--f-gold);
            font-weight: 900;
            font-size: 1.2rem;
        }

        .control-image-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        .control-image {
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(0, 102, 255, 0.15);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.5);
            background: rgba(10, 42, 74, 0.2);
            padding: 10px;
            width: 100%;
        }

        .control-image img {
            width: 100%;
            height: auto;
            display: block;
            border-radius: 12px;
            opacity: 0.95;
            transition: 0.3s;
        }

        .control-image:hover img {
            opacity: 1;
        }

        .btn-download-brochure {
            display: inline-block;
            padding: 12px 30px;
            background: var(--f-blue-electric);
            color: #fff;
            font-family: var(--font-mono);
            text-decoration: none;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 700;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0, 102, 255, 0.3);
        }

        .btn-download-brochure:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(0, 102, 255, 0.5);
        }

        /* ---------------------------------------------
           8. SECCIÓN 4: TABLA COMPLETA
        --------------------------------------------- */
        .f-table-section {
            background: var(--f-black);
            padding: var(--section-padding-desktop);
            position: relative;
            overflow: hidden;
            border-top: 1px solid rgba(0, 102, 255, 0.05);
        }

        .table-container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(10, 42, 74, 0.2);
            padding: 40px;
            border-radius: 24px;
            border: 1px solid rgba(0, 102, 255, 0.1);
            backdrop-filter: blur(4px);
        }

        .feature-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.95rem;
            color: var(--f-gray-light);
        }

        .feature-table th {
            background: rgba(0, 102, 255, 0.15);
            color: var(--f-blue-electric);
            padding: 18px;
            text-align: left;
            font-family: var(--font-mono);
            border-bottom: 2px solid rgba(0, 102, 255, 0.3);
        }

        .feature-table td {
            padding: 15px 18px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            vertical-align: top;
        }

        .feature-table tr:last-child td {
            border-bottom: none;
        }

        .feature-table tr:hover {
            background-color: rgba(0, 102, 255, 0.05);
        }

        .tag {
            background: rgba(245, 166, 35, 0.15);
            color: var(--f-gold);
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            display: inline-block;
            margin-right: 5px;
            margin-bottom: 5px;
        }

        /* ---------------------------------------------
           9. SECCIÓN 5: PRÓXIMAMENTE 25.0 (Solo Candado + Texto)
        --------------------------------------------- */
        .f-coming-section {
            background: var(--f-black);
            padding: var(--section-padding-desktop);
            position: relative;
            overflow: hidden;
            text-align: center;
            border-top: 1px solid rgba(0, 102, 255, 0.05);
        }

        .coming-container {
            position: relative;
            z-index: 2;
            max-width: 600px;
            margin: 0 auto;
        }

        .coming-card {
            background: linear-gradient(145deg, rgba(10, 42, 74, 0.8), rgba(0, 0, 0, 0.6));
            border: 1px solid rgba(0, 102, 255, 0.2);
            border-radius: 24px;
            padding: 60px 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.8);
            position: relative;
        }

        .padlock-3d-container {
            width: 100px;
            height: 100px;
            margin: 0 auto 25px;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .padlock-3d {
            position: absolute;
            bottom: 0;
            right: 0;
            font-size: 3.5rem;
            animation: unlockChest 3s ease-in-out infinite;
            transform-origin: bottom center;
            filter: drop-shadow(0 0 20px rgba(245, 166, 35, 0.6));
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.8);
        }

        .coming-card h3 {
            font-family: var(--font-title);
            font-size: 2.5rem;
            color: var(--f-white);
            margin-bottom: 10px;
        }

        .coming-card h3 span {
            color: var(--f-gold);
        }

        .coming-card p {
            color: var(--f-gray-light);
            font-size: 1.1rem;
            letter-spacing: 2px;
            font-weight: 600;
        }

        /* ---------------------------------------------
           10. FOOTER + MAPA LEAFLET (DARK MODE)
        --------------------------------------------- */
        .f-footer {
            background: var(--f-gray-dark);
            padding: 80px 5% 40px;
            border-top: 1px solid rgba(0, 102, 255, 0.1);
        }

        .footer-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: start;
        }

        .footer-map-container h3 {
            font-family: var(--font-title);
            color: var(--f-blue-electric);
            font-size: 1.8rem;
            margin-bottom: 20px;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .footer-map {
            border-radius: 16px;
            overflow: hidden;
            border: 1px solid rgba(0, 102, 255, 0.1);
            height: 300px;
            background: #1a1a1a;
        }

        #map {
            width: 100%;
            height: 100%;
        }

        .footer-info h4 {
            font-family: var(--font-mono);
            font-size: 1.2rem;
            color: var(--f-blue-electric);
            margin-bottom: 20px;
            letter-spacing: 1px;
        }

        .footer-info p {
            color: var(--f-gray-light);
            font-size: 0.95rem;
            line-height: 2;
            margin-bottom: 8px;
        }

        .footer-info p strong {
            color: var(--f-white);
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 40px auto 0;
            padding-top: 25px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .footer-bottom .copy {
            color: #444;
            font-size: 0.75rem;
        }

        .footer-credit {
            color: var(--f-white);
            font-weight: 600;
            font-size: 0.95rem;
            text-align: center;
            width: 100%;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        .footer-credit a {
            color: #d32f2f;
            text-decoration: none;
            font-weight: 800;
            transition: 0.3s;
        }

        .footer-credit a:hover {
            text-decoration: underline;
            opacity: 0.8;
        }

        /* ---------------------------------------------
           11. WHATSAPP FLOTANTE
        --------------------------------------------- */
        .wa-float-btn {
            position: fixed;
            bottom: 35px;
            right: 35px;
            width: 70px;
            height: 70px;
            background: #25D366;
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 9999;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
            text-decoration: none;
        }

        .wa-float-btn:hover {
            background: #20b859;
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.4);
        }

        .wa-icon-svg {
            width: 38px;
            height: 38px;
            fill: #FFFFFF;
        }

        /* ---------------------------------------------
           12. MODAL TRIPLE PASO (Nombre -> 4 Tarjetas -> Fecha/Hora Full)
        --------------------------------------------- */
        .f-modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(15px);
            z-index: 99999;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .f-modal-overlay.active {
            display: flex;
        }

        .f-modal-container {
            background: rgba(10, 42, 74, 0.95);
            border: 1px solid rgba(0, 102, 255, 0.2);
            border-radius: 24px;
            max-width: 550px;
            width: 100%;
            padding: 45px 40px;
            position: relative;
            box-shadow: 0 40px 80px rgba(0, 0, 0, 0.6);
            max-height: 90vh;
            overflow-y: auto;
        }

        .f-modal-close {
            position: absolute;
            top: 18px;
            right: 22px;
            color: rgba(255, 255, 255, 0.4);
            font-size: 28px;
            cursor: pointer;
            transition: 0.3s;
            background: none;
            border: none;
            font-family: var(--font-main);
        }

        .f-modal-close:hover {
            color: var(--f-white);
            transform: rotate(90deg);
        }

        .f-modal-step {
            display: none;
            animation: fadeInUp 0.4s ease;
        }

        .f-modal-step.active {
            display: block;
        }

        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }

            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .f-modal-step h3 {
            font-family: var(--font-title);
            font-size: 1.8rem;
            color: var(--f-white);
            margin-bottom: 15px;
        }

        .f-modal-step .step-sub {
            color: var(--f-gray-light);
            font-size: 0.9rem;
            margin-bottom: 30px;
        }

        .f-modal-step input[type="text"] {
            width: 100%;
            padding: 16px 20px;
            background: rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(0, 102, 255, 0.2);
            border-radius: 12px;
            color: var(--f-white);
            font-size: 1rem;
            outline: none;
            transition: 0.3s;
        }

        .f-modal-step input[type="text"]:focus {
            border-color: var(--f-blue-electric);
            box-shadow: 0 0 20px rgba(0, 102, 255, 0.1);
        }

        .sector-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin: 25px 0;
        }

        .sector-card {
            background: rgba(0, 0, 0, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.05);
            border-radius: 16px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            color: var(--f-gray-light);
            font-weight: 600;
        }

        .sector-card:hover {
            border-color: var(--f-blue-electric);
            background: rgba(0, 102, 255, 0.05);
        }

        .sector-card.selected {
            border-color: var(--f-gold);
            background: rgba(245, 166, 35, 0.1);
            box-shadow: 0 0 25px rgba(245, 166, 35, 0.1);
            color: var(--f-white);
        }

        .sector-card .sector-icon {
            font-size: 2rem;
            display: block;
            margin-bottom: 8px;
        }

        /* Estilos del Paso 3 (Full Fecha) */
        .f-modal-step-full {}

        .f-modal-step-full .f-calendar-wrap {
            margin: 20px 0;
        }

        .f-modal-step-full .f-calendar-nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .f-modal-step-full .f-calendar-nav button {
            background: none;
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--f-white);
            padding: 8px 16px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            transition: 0.3s;
        }

        .f-modal-step-full .f-calendar-nav button:hover {
            border-color: var(--f-blue-electric);
        }

        .f-modal-step-full .f-calendar-nav .month-label {
            font-family: var(--font-mono);
            font-size: 0.9rem;
            color: var(--f-gold);
        }

        .f-modal-step-full .f-calendar-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 8px;
        }

        .f-modal-step-full .f-calendar-grid .day-label {
            font-size: 0.7rem;
            color: #666;
            text-align: center;
            padding: 6px 0;
            font-family: var(--font-mono);
        }

        .f-modal-step-full .f-calendar-grid .day-cell {
            padding: 12px 0;
            text-align: center;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s;
            font-size: 0.85rem;
            color: var(--f-gray-light);
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid transparent;
        }

        .f-modal-step-full .f-calendar-grid .day-cell:hover {
            border-color: var(--f-blue-electric);
            background: rgba(0, 102, 255, 0.05);
        }

        .f-modal-step-full .f-calendar-grid .day-cell.selected {
            background: var(--f-blue-electric);
            color: var(--f-white);
            border-color: var(--f-blue-electric);
            box-shadow: 0 0 15px rgba(0, 102, 255, 0.4);
        }

        .f-modal-step-full .f-calendar-grid .day-cell.other-month {
            opacity: 0.3;
            pointer-events: none;
        }

        .f-modal-step-full .f-calendar-grid .day-cell.disabled {
            opacity: 0.2;
            pointer-events: none;
        }

        .f-modal-step-full .f-time-select {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-top: 20px;
            justify-content: center;
        }

        .f-modal-step-full .f-time-select .time-slot {
            padding: 12px 25px;
            border-radius: 50px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            background: rgba(0, 0, 0, 0.3);
            color: var(--f-gray-light);
            cursor: pointer;
            transition: 0.3s;
            font-size: 0.85rem;
            font-family: var(--font-mono);
        }

        .f-modal-step-full .f-time-select .time-slot:hover {
            border-color: var(--f-blue-electric);
        }

        .f-modal-step-full .f-time-select .time-slot.selected {
            background: var(--f-blue-electric);
            color: var(--f-white);
            border-color: var(--f-blue-electric);
            box-shadow: 0 0 15px rgba(0, 102, 255, 0.4);
        }

        .f-modal-btn {
            width: 100%;
            padding: 18px;
            background: var(--f-blue-electric);
            border: none;
            border-radius: 12px;
            color: var(--f-white);
            font-family: var(--font-mono);
            font-weight: 900;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 25px;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .f-modal-btn:hover {
            background: #0044CC;
            box-shadow: 0 0 30px rgba(0, 102, 255, 0.3);
            transform: translateY(-2px);
        }

        .f-modal-btn:disabled {
            opacity: 0.4;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .step-counter {
            text-align: center;
            margin-top: 25px;
            font-size: 0.7rem;
            color: #555;
            font-family: var(--font-mono);
            letter-spacing: 1px;
        }

        /* ---------------------------------------------
           13. MEDIA QUERIES (MÁS ANCHO EN MÓVIL)
        --------------------------------------------- */
        @media (max-width: 992px) {
            .modules-grid {
                grid-template-columns: 1fr 1fr;
            }

            .control-container {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .control-image {
                order: -1;
            }

            .footer-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
        }

        @media (max-width: 768px) {
            :root {
                --section-padding-desktop: 80px 5%;
                --card-padding: 30px 25px;
                --gap-lg: 30px;
            }

            .headline {
                font-size: 2.5rem;
            }

            .cta-premium {
                width: 100%;
                padding: 18px 20px;
                font-size: 0.9rem;
            }

            .modules-grid {
                grid-template-columns: 1fr;
            }

            /* Tarjetas y texto más anchos en móvil */
            .module-card p {
                font-size: 1rem;
                line-height: 1.6;
                width: 100%;
            }

            .sector-grid {
                grid-template-columns: 1fr 1fr;
            }

            .f-modal-container {
                padding: 30px 20px;
                max-width: 95%;
            }

            .wa-float-btn {
                bottom: 20px;
                right: 20px;
                width: 60px;
                height: 60px;
            }

            .wa-icon-svg {
                width: 33px;
                height: 33px;
            }

            .f-modal-step-full .f-calendar-grid .day-cell {
                padding: 10px 0;
                font-size: 0.8rem;
            }

            .f-modal-step-full .f-time-select .time-slot {
                padding: 10px 18px;
                font-size: 0.8rem;
            }
        }
    </style>
</head>

<body>

    <!-- PRELOADER -->
    <div id="preloader">
        <div class="loader-wrap">
            <div class="fortuner-loader-logo">
                <div class="arc arc1"></div>
                <div class="arc arc2"></div>
                <div class="arc arc3"></div>
                <div class="center-core"></div>
            </div>
            <div class="loader-text">Ingresando al <span>Sistema...</span></div>
            <div class="loader-bar">
                <div class="loader-bar-fill"></div>
            </div>
        </div>
    </div>

    <!-- BARRA DE PODER TECNOLÓGICA -->
    <div class="power-bar">
        <div class="power-energy"></div>
    </div>

    <!-- HERO -->
    <main class="main-engine">
        <div class="tech-brain-bg">
            <div class="neuron"></div>
            <div class="neuron"></div>
            <div class="neuron"></div>
            <div class="circuit-line"></div>
            <div class="circuit-line"></div>
            <div class="circuit-line"></div>
            <div class="particle"></div>
            <div class="particle"></div>
            <div class="particle"></div>
            <div class="particle"></div>
        </div>

        <div class="content-box">
            <h1 class="headline">¿Su negocio aún<br><span>no está conectado?</span></h1>
            <p class="paragraph"><strong>Fortuner ERP</strong> integra ventas, finanzas e inventarios en una sola
                plataforma. Controle su operación con datos precisos y en tiempo real.</p>
            <a class="cta-premium" id="openModalBtn">Agendar Demostración →</a>
        </div>
    </main>

    <!-- CATÁLOGO DE MÓDULOS -->
    <section class="f-modules-section">
        <div class="bg-tech-pattern"></div>
        <div class="modules-container">
            <h2 class="modules-title">Adaptado al <span>crecimiento</span> de su marca</h2>
            <div class="modules-grid">
                <div class="module-card">
                    <div class="module-img-wrapper" onclick="openImageModal('image/Facturacion.webp')">
                        <img src="image/Facturacion.webp" alt="Facturación Fortuner" loading="lazy">
                    </div>
                    <h3>FACTURACIÓN</h3>
                    <p>Optimice sus ventas. Facturación electrónica, POS y control de turnos. Agilice cada transacción
                        para una mejor experiencia de compra.</p>
                    <a href="https://wa.me/573159276091?text=Hola%2C%20quiero%20mejorar%20la%20facturaci%C3%B3n%20de%20mi%20negocio%20con%20Fortuner"
                        target="_blank" class="btn-module">Conocer más →</a>
                </div>
                <div class="module-card">
                    <div class="module-img-wrapper" onclick="openImageModal('image/Inventario.webp')">
                        <img src="image/Inventario.webp" alt="Inventario Fortuner" loading="lazy">
                    </div>
                    <h3>INVENTARIO</h3>
                    <p>Controle el stock en tiempo real. Gestione compras, lotes y pronósticos de demanda para eliminar
                        quiebres de inventario.</p>
                    <a href="https://wa.me/573159276091?text=Hola%2C%20quiero%20optimizar%20el%20inventario%20de%20mi%20negocio%20con%20Fortuner"
                        target="_blank" class="btn-module">Conocer más →</a>
                </div>
                <div class="module-card">
                    <div class="module-img-wrapper" onclick="openImageModal('image/Contabilidad.webp')">
                        <img src="image/Contabilidad.webp" alt="Contabilidad Fortuner" loading="lazy">
                    </div>
                    <h3>CONTABILIDAD</h3>
                    <p>Automatice su gestión financiera. Balances, flujo de caja e informes NIC. Tome decisiones
                        estratégicas con datos precisos y fiables.</p>
                    <a href="https://wa.me/573159276091?text=Hola%2C%20quiero%20automatizar%20la%20contabilidad%20de%20mi%20negocio%20con%20Fortuner"
                        target="_blank" class="btn-module">Conocer más →</a>
                </div>
            </div>
        </div>
    </section>

    <!-- PANEL DE CONTROL -->
    <section class="f-control-section">
        <div class="control-container">
            <div class="control-text">
                <h2>Controle cada <span class="highlight">área</span> de su empresa</h2>
                <p>Fortuner ERP le brinda una visión 360° de su negocio. Desde el punto de venta hasta los informes
                    gerenciales, todo en un solo lugar.</p>
                <ul class="feature-list">
                    <li>Dashboard ejecutivo en tiempo real</li>
                    <li>Integración nativa con tiendas online</li>
                    <li>Acceso móvil para supervisores y gerentes</li>
                    <li>Reportes automáticos y análisis predictivo</li>
                </ul>
            </div>
            <div class="control-image-wrapper">
                <div class="control-image">
                    <img src="image/Panel.webp" alt="Panel de Control Fortuner" loading="lazy">
                </div>
                <a href="Descargables/Brochure-Fortuner-2025.pdf" download class="btn-download-brochure">⬇ DESCARGAR
                    BROCHURE</a>
            </div>
        </div>
    </section>

    <!-- TABLA 100% FUNCIONALIDAD -->
    <section class="f-table-section">
        <div class="modules-container">
            <h2 class="modules-title">Cobertura <span>Total</span> del Sistema</h2>
            <div class="table-container">
                <div style="overflow-x: auto;">
                    <table class="feature-table">
                        <thead>
                            <tr>
                                <th>Módulo / Herramienta</th>
                                <th>Funciones Clave</th>
                                <th>Sector Aplicable</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>Gestión Punto de Venta</strong></td>
                                <td>POS, Domicilios, Fidelización, Integración Datafonos, Kioskos, Autopagos</td>
                                <td><span class="tag">Retail</span> <span class="tag">Supermercados</span></td>
                            </tr>
                            <tr>
                                <td><strong>Gestión Logística</strong></td>
                                <td>Compras, Inventarios, Producción, CEDI, Traslados, EDI</td>
                                <td><span class="tag">Distribuidoras</span> <span class="tag">Logística</span></td>
                            </tr>
                            <tr>
                                <td><strong>Gestión Financiera</strong></td>
                                <td>Contabilidad, Facturación Electrónica, Cartera, Bancos, Costos ABC</td>
                                <td><span class="tag">Financiero</span> <span class="tag">Servicios</span></td>
                            </tr>
                            <tr>
                                <td><strong>Gestión Operativa</strong></td>
                                <td>E-Commerce, Taller Vehículos, Restaurantes, Acueductos</td>
                                <td><span class="tag">Manufactura</span> <span class="tag">Hospitalidad</span></td>
                            </tr>
                            <tr>
                                <td><strong>Gestión Administrativa</strong></td>
                                <td>Nómina Electrónica, RRHH, Analítica de Negocios (BI - Power BI/Tableau)</td>
                                <td><span class="tag">Empresas</span> <span class="tag">Industrias</span></td>
                            </tr>
                            <tr>
                                <td><strong>Movilidad</strong></td>
                                <td>App Móvil para pedidos, Pronósticos de demanda, Gestión en campo</td>
                                <td><span class="tag">Comercial</span> <span class="tag">Campo</span></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </section>

    <!-- PRÓXIMAMENTE 25.0 (SOLO CANDADO 3D) -->
    <section class="f-coming-section">
        <div class="coming-container">
            <div class="coming-card">
                <div class="padlock-3d-container">
                    <div class="padlock-3d">🔓</div>
                </div>
                <h3>Próximamente <span>25.0</span></h3>
                <p>Nueva versión - Noviembre 2026</p>
            </div>
        </div>
    </section>

    <!-- FOOTER + MAPA LEAFLET -->
    <footer class="f-footer">
        <div class="footer-grid">
            <div class="footer-map-container">
                <h3>NUESTRA COBERTURA</h3>
                <div class="footer-map">
                    <div id="map"></div>
                </div>
            </div>
            <div class="footer-info">
                <h4>CONTACTO FORTUNER</h4>
                <p><strong>📞 Teléfono Único:</strong> 315 927 6091</p>
                <p><strong>🕒 Horario:</strong> Lunes a Viernes, 8:00 AM - 6:00 PM</p>
                <p><strong>📍 Cobertura:</strong> Nacional (Colombia)</p>
            </div>
        </div>
        <div class="footer-bottom">
            <div class="copy">&copy; 2026 Fortuner ERP. Todos los derechos reservados.</div>
        </div>
        <div class="footer-credit">
            Echo con pasión 🔥 por <a href="https://redsapien.com/" target="_blank">RedSapien</a>
        </div>
    </footer>

    <!-- WHATSAPP FLOTANTE -->
    <a href="https://wa.me/573159276091?text=Hola%20Fortuner%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20el%20ERP"
        class="wa-float-btn" target="_blank" rel="noopener noreferrer">
        <svg class="wa-icon-svg" viewBox="0 0 24 24">
            <path
                d="M12.032 1.999c-5.514 0-10 4.486-10 9.999 0 1.763.457 3.475 1.323 4.982l-1.343 4.846 4.96-1.308c1.456.792 3.119 1.211 4.828 1.211 5.514 0 10-4.486 10-10s-4.486-10-10-10zm0 18.5c-1.497 0-2.96-.4-4.239-1.155l-.295-.176-2.944.777.787-2.864-.192-.305c-1.395-2.221-1.512-4.784-.238-6.981 1.16-2.002 3.352-3.239 5.734-3.239 3.585 0 6.5 2.915 6.5 6.5s-2.915 6.5-6.5 6.5zm3.729-4.857c-.2-.098-1.164-.574-1.344-.639s-.31-.098-.441.098c-.131.196-.51.64-.625.771s-.23.149-.429.05c-.92-.46-1.94-1.139-2.653-2.035-.275-.346-.717-.896-.111-1.045.282-.069.439-.23.534-.365.045-.069.078-.13.12-.216.03-.064.02-.121-.01-.172-.03-.05-.418-1.007-.577-1.383-.153-.362-.309-.312-.425-.315l-.363-.013c-.122 0-.327.046-.498.232-.247.27-.855.835-.855 2.037 0 1.202.875 2.363.997 2.526.122.165 1.724 2.631 4.176 3.688.416.179.791.254 1.084.267.453.022 1.311.019 1.774-.099.575-.147 1.157-.605 1.32-1.189.163-.584.163-1.082.114-1.185-.047-.102-.172-.166-.372-.265z" />
        </svg>
    </a>

    <!-- MODAL 3 PASOS (Nombre -> Sector -> Fecha Full) -->
    <div class="f-modal-overlay" id="fModal">
        <div class="f-modal-container">
            <button class="f-modal-close" id="closeModalBtn">✕</button>

            <!-- PASO 1: NOMBRE -->
            <div class="f-modal-step active" data-step="1">
                <h3>¿Cómo se llama su negocio?</h3>
                <p class="step-sub">Ingrese el nombre de su empresa o emprendimiento.</p>
                <input type="text" id="businessName" placeholder="Ej: Distribuidora XYZ" autofocus>
                <button class="f-modal-btn" id="step1Btn">Siguiente →</button>
                <div class="step-counter">Paso 1 de 3</div>
            </div>

            <!-- PASO 2: SECTOR (Solo 4 tarjetas) -->
            <div class="f-modal-step" data-step="2">
                <h3>Seleccione su sector</h3>
                <p class="step-sub">Elija su industria para continuar.</p>
                <div class="sector-grid" id="sectorGrid">
                    <div class="sector-card" data-sector="Supermercados"><span
                            class="sector-icon">🛒</span>Supermercados</div>
                    <div class="sector-card" data-sector="Minoristas"><span class="sector-icon">🏪</span>Minoristas
                    </div>
                    <div class="sector-card" data-sector="Gastronomía"><span class="sector-icon">🍽️</span>Gastronomía
                    </div>
                    <div class="sector-card" data-sector="Logística"><span class="sector-icon">🚚</span>Logística</div>
                </div>
                <div class="step-counter">Paso 2 de 3</div>
            </div>
        </div>
    </div>

    <!-- MODAL FULL (PASO 3: FECHA/HORA) - APARECE EN PANTALLA COMPLETA -->
    <div class="f-modal-overlay" id="fModalFull" style="z-index: 999999; background: rgba(0,0,0,0.95);">
        <div class="f-modal-container" style="max-width: 700px; padding: 50px 40px;">
            <button class="f-modal-close" onclick="closeFullModal()">✕</button>
            <div class="f-modal-step-full">
                <h3>Agende su demostración</h3>
                <p class="step-sub" style="color:var(--f-gray-light); margin-bottom: 30px;">Seleccione la fecha y hora
                    ideales para usted.</p>

                <div class="f-calendar-wrap">
                    <div class="f-calendar-nav">
                        <button id="prevMonthFull">‹</button>
                        <span class="month-label" id="monthLabelFull">Enero 2026</span>
                        <button id="nextMonthFull">›</button>
                    </div>
                    <div class="f-calendar-grid" id="calendarGridFull"></div>
                </div>

                <div class="f-time-select" id="timeSelectFull">
                    <div class="time-slot" data-time="09:00">09:00 AM</div>
                    <div class="time-slot" data-time="11:00">11:00 AM</div>
                    <div class="time-slot" data-time="14:00">02:00 PM</div>
                    <div class="time-slot" data-time="16:00">04:00 PM</div>
                </div>

                <button class="f-modal-btn" id="step3Btn" disabled style="margin-top: 30px;">Confirmar y Agendar
                    📞</button>
            </div>
        </div>
    </div>

    <!-- IMAGE MODAL -->
    <div id="imageModal"
        style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.95); z-index:999999; align-items:center; justify-content:center; padding:20px; cursor:pointer;"
        onclick="closeImageModal()">
        <img id="imageModalImg" src="" alt="Ampliar"
            style="max-width:90%; max-height:90vh; border-radius:12px; border:1px solid rgba(0,102,255,0.2);">
        <button
            style="position:absolute; top:25px; right:30px; background:rgba(255,255,255,0.1); border:none; color:#fff; font-size:30px; cursor:pointer; width:50px; height:50px; border-radius:50%; transition:0.3s;"
            onclick="closeImageModal()">✕</button>
    </div>

    <!-- SCRIPTS -->
    <script src="https://kit.fontawesome.com/a09bc6c7f9.js" crossorigin="anonymous" async></script>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

    <script>
        // 1. PRELOADER
        window.addEventListener('load', function () {
            setTimeout(function () {
                const preloader = document.getElementById('preloader');
                preloader.style.opacity = '0';
                setTimeout(() => { preloader.style.display = 'none'; document.body.style.overflow = 'auto'; }, 600);
            }, 2000); // 2 segundos
        });

        // 2. MAPA LEAFLET (DARK MODE + COLOMBIA)
        document.addEventListener('DOMContentLoaded', function () {
            const mapContainer = document.getElementById('map');
            if (mapContainer) {
                const map = L.map('map', { zoomControl: false }).setView([5.0, -75.0], 6);
                L.tileLayer('https://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png', {
                    attribution: '&copy; OpenStreetMap &copy; CartoDB', subdomains: 'abcd', maxZoom: 19
                }).addTo(map);

                const cities = [
                    { name: "Manizales", coords: [5.0689, -75.5174] },
                    { name: "Pereira", coords: [4.8087, -75.6906] },
                    { name: "Medellín", coords: [6.2442, -75.5812] },
                    { name: "Bogotá", coords: [4.7110, -74.0721] }
                ];

                cities.forEach(city => {
                    const marker = L.marker(city.coords, {
                        icon: L.divIcon({
                            className: 'custom-pulse-icon',
                            html: `<div style="background:#0066FF; width:14px; height:14px; border-radius:50%; box-shadow: 0 0 20px #0066FF; border:2px solid #fff;"></div>`,
                            iconSize: [14, 14], iconAnchor: [7, 7]
                        })
                    }).addTo(map);
                    marker.bindPopup(`<b style="color:#0A2A4A;">FORTUNER</b><br>${city.name}`);
                });

                const group = L.featureGroup(cities.map(c => L.marker(c.coords)));
                map.fitBounds(group.getBounds().pad(0.2));
            }
        });

        // 3. MODAL FLUJO PERFECTO
        const modal = document.getElementById('fModal');
        const modalFull = document.getElementById('fModalFull');
        const openBtns = document.querySelectorAll('#openModalBtn, #openModalBtn2');
        const closeBtn = document.getElementById('closeModalBtn');
        const steps = document.querySelectorAll('.f-modal-step');
        const step1Btn = document.getElementById('step1Btn');
        const businessNameInput = document.getElementById('businessName');
        const sectorCards = document.querySelectorAll('.sector-card');

        let formData = { businessName: '', sector: '', date: '', time: '' };
        let selectedDate = null, selectedTime = null;
        let currentMonth = new Date().getMonth();
        let currentYear = new Date().getFullYear();

        // Abrir modal inicial
        function openModal() { modal.classList.add('active'); document.body.style.overflow = 'hidden'; resetModal(); }
        function closeModal() { modal.classList.remove('active'); document.body.style.overflow = 'auto'; }
        openBtns.forEach(btn => btn.addEventListener('click', openModal));
        closeBtn.addEventListener('click', closeModal);
        modal.addEventListener('click', e => { if (e.target === modal) closeModal(); });

        function resetModal() {
            steps.forEach((s, i) => s.classList.toggle('active', i === 0));
            businessNameInput.value = ''; businessNameInput.focus();
            formData = { businessName: '', sector: '', date: '', time: '' };
            document.querySelectorAll('.sector-card').forEach(c => c.classList.remove('selected'));
            selectedDate = null; selectedTime = null;
            step1Btn.disabled = false;
        }

        // Paso 1
        step1Btn.addEventListener('click', function () {
            const name = businessNameInput.value.trim();
            if (!name) { alert("Por favor, ingrese el nombre de su negocio."); return; }
            formData.businessName = name;
            goToStep(2);
        });
        businessNameInput.addEventListener('keydown', e => { if (e.key === 'Enter') step1Btn.click(); });

        function goToStep(step) { steps.forEach((s, i) => s.classList.toggle('active', i === step - 1)); }

        // Paso 2: Selección de Sector (Abre el Modal Full automáticamente)
        sectorCards.forEach(card => {
            card.addEventListener('click', function () {
                sectorCards.forEach(c => c.classList.remove('selected'));
                this.classList.add('selected');
                formData.sector = this.dataset.sector;

                // Cerrar modal pequeño y abrir modal FULL
                closeModal();
                setTimeout(() => { openFullModal(); }, 400);
            });
        });

        // ---------------------------------------------
        // 4. MODAL FULL (FECHA Y HORA)
        // ---------------------------------------------
        function openFullModal() { modalFull.classList.add('active'); document.body.style.overflow = 'hidden'; renderCalendarFull(currentMonth, currentYear); }
        function closeFullModal() { modalFull.classList.remove('active'); document.body.style.overflow = 'auto'; }
        modalFull.addEventListener('click', e => { if (e.target === modalFull) closeFullModal(); });

        function renderCalendarFull(month, year) {
            const grid = document.getElementById('calendarGridFull');
            const monthLabel = document.getElementById('monthLabelFull');
            const months = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'];
            monthLabel.textContent = months[month] + ' ' + year;

            const firstDay = new Date(year, month, 1).getDay();
            const daysInMonth = new Date(year, month + 1, 0).getDate();
            const today = new Date();

            let html = '<div class="day-label">L</div><div class="day-label">M</div><div class="day-label">M</div><div class="day-label">J</div><div class="day-label">V</div><div class="day-label">S</div><div class="day-label">D</div>';
            const startOffset = firstDay === 0 ? 6 : firstDay - 1;
            for (let i = 0; i < startOffset; i++) html += `<div class="day-cell other-month"></div>`;

            for (let d = 1; d <= daysInMonth; d++) {
                const isPast = new Date(year, month, d) < new Date(today.getFullYear(), today.getMonth(), today.getDate());
                const classes = ['day-cell'];
                if (isPast) classes.push('disabled');
                if (selectedDate === `${year}-${String(month + 1).padStart(2, '0')}-${String(d).padStart(2, '0')}`) classes.push('selected');
                html += `<div class="${classes.join(' ')}" data-date="${year}-${String(month + 1).padStart(2, '0')}-${String(d).padStart(2, '0')}">${d}</div>`;
            }
            grid.innerHTML = html;

            grid.querySelectorAll('.day-cell:not(.other-month):not(.disabled)').forEach(cell => {
                cell.addEventListener('click', function () {
                    grid.querySelectorAll('.day-cell').forEach(c => c.classList.remove('selected'));
                    this.classList.add('selected');
                    selectedDate = this.dataset.date;
                    formData.date = selectedDate;
                    checkFullComplete();
                });
            });

            document.querySelectorAll('#timeSelectFull .time-slot').forEach(slot => {
                slot.addEventListener('click', function () {
                    document.querySelectorAll('#timeSelectFull .time-slot').forEach(s => s.classList.remove('selected'));
                    this.classList.add('selected');
                    selectedTime = this.dataset.time;
                    formData.time = selectedTime;
                    checkFullComplete();
                });
            });

            document.getElementById('prevMonthFull').onclick = function () {
                if (month === 0) { currentMonth = 11; currentYear--; } else { currentMonth--; }
                renderCalendarFull(currentMonth, currentYear);
            };
            document.getElementById('nextMonthFull').onclick = function () {
                if (month === 11) { currentMonth = 0; currentYear++; } else { currentMonth++; }
                renderCalendarFull(currentMonth, currentYear);
            };
        }

        function checkFullComplete() {
            const btn = document.getElementById('step3Btn');
            btn.disabled = !(selectedDate && selectedTime);
        }

        document.getElementById('step3Btn').addEventListener('click', function () {
            if (!selectedDate || !selectedTime) { alert("Por favor, complete todos los datos."); return; }
            const msg = `*Nueva demostración Fortuner ERP*%0A%0A*Negocio:* ${encodeURIComponent(formData.businessName)}%0A*Sector:* ${encodeURIComponent(formData.sector)}%0A*Fecha:* ${encodeURIComponent(formData.date)}%0A*Hora:* ${encodeURIComponent(formData.time)}`;
            window.open(`https://wa.me/573159276091?text=${msg}`, '_blank');
            closeFullModal();
        });

        // 5. IMAGE MODAL
        function openImageModal(src) { document.getElementById('imageModal').style.display = 'flex'; document.getElementById('imageModalImg').src = src; document.body.style.overflow = 'hidden'; }
        function closeImageModal() { document.getElementById('imageModal').style.display = 'none'; document.body.style.overflow = 'auto'; }
        document.addEventListener('keydown', e => { if (e.key === 'Escape') { closeImageModal(); if (modal.classList.contains('active')) closeModal(); if (modalFull.classList.contains('active')) closeFullModal(); } });
    </script>
</body>

</html>

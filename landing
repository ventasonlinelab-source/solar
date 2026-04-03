<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PROTOCOLO 10X² | ESCALA SOLAR</title>
    <style>
        :root { --bg: #050505; --text: #e0e0e0; --accent: #00ff66; --grey: #121212; --font: 'Courier New', monospace; }
        body { background: var(--bg); color: var(--text); font-family: var(--font); margin: 0; display: flex; align-items: center; justify-content: center; min-height: 100vh; overflow-x: hidden; }
        
        #terminal { background: rgba(10,10,10,0.98); border: 2px solid var(--accent); padding: 40px; width: 95%; max-width: 750px; box-shadow: 0 0 100px rgba(0,255,102,0.1); position: relative; }
        
        .header-box { text-align: center; margin-bottom: 35px; }
        h1 { font-size: 2.1rem; color: #fff; text-transform: uppercase; margin: 0 0 15px 0; line-height: 1.1; letter-spacing: -1px; }
        h1 span { color: var(--accent); }
        .sub-header { font-size: 1.1rem; color: #bbb; line-height: 1.5; max-width: 90%; margin: 0 auto; }
        .sub-header b { color: var(--accent); border-bottom: 1px solid var(--accent); }

        .progress-container { height: 4px; background: #222; margin: 30px 0; width: 100%; }
        .progress-fill { height: 100%; background: var(--accent); width: 25%; transition: 0.6s cubic-bezier(0.19, 1, 0.22, 1); box-shadow: 0 0 15px var(--accent); }

        .quiz-step { display: none; }
        .quiz-step.active { display: block; animation: fadeIn 0.4s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        .question-text { font-size: 1.1rem; margin-bottom: 25px; color: var(--accent); font-weight: bold; text-transform: uppercase; letter-spacing: 1px; }

        /* EL DIAGNÓSTICO DE SELECCIÓN */
        .option-card { 
            background: var(--grey); border: 1px solid #333; color: var(--text); padding: 22px; 
            margin-bottom: 12px; cursor: pointer; transition: 0.2s; display: flex; align-items: center;
            text-transform: uppercase; font-size: 0.9rem; font-weight: 700;
        }
        .option-card:hover { border-color: var(--accent); background: #0a1f14; color: var(--accent); transform: translateX(10px); }
        .option-card::before { content: "[ ]"; margin-right: 15px; color: #444; font-family: monospace; }
        .option-card:hover::before { content: "[X]"; color: var(--accent); }

        .vsl-box { background: #000; border: 1px solid var(--accent); padding: 15px; margin-bottom: 25px; text-align: center; }

        .form-input { width: 100%; background: #000; border: 1px solid #333; padding: 20px; color: var(--accent); font-family: var(--font); box-sizing: border-box; font-size: 1.1rem; margin-bottom: 15px; }
        .form-input:focus { border-color: var(--accent); outline: none; }

        .submit-btn { width: 100%; background: var(--accent); color: #000; border: none; padding: 28px; font-weight: 900; cursor: pointer; text-transform: uppercase; font-size: 1.3rem; transition: 0.3s; }
        .submit-btn:hover { background: #fff; box-shadow: 0 0 50px var(--accent); transform: scale(1.02); }

        .nav-link { color: #444; text-decoration: underline; font-size: 0.8rem; cursor: pointer; display: inline-block; margin-top: 20px; }
        .nav-link:hover { color: #fff; }
    </style>
</head>
<body>

    <div id="terminal">
        <div class="header-box">
            <h1>DUPLICA TU <span>BENEFICIO NETO</span> EN 7 DÍAS SIN INSTALAR NI UN TEJADO MÁS</h1>
            <p class="sub-header">Eliminamos el caos operativo conectando Captación y Odoo. <b>Garantizado por contrato</b>: Recupera el control de tus márgenes <b>sin mover un dedo</b>.</p>
        </div>

        <div class="progress-container"><div class="progress-fill" id="bar"></div></div>

        <div class="quiz-step active" id="step1">
            <p class="question-text">> IDENTIFICA TU PUNTO DE FUGA:</p>
            <div class="option-card" onclick="select(1, 'MUCHO_VOL_POCO_BEN', 2)">Facturo mucho pero mi beneficio neto es ridículo</div>
            <div class="option-card" onclick="select(1, 'CAOS_ODOO', 2)">Tengo un desorden total en leads y Odoo</div>
            <div class="option-card" onclick="select(1, 'TECHO_ESCALA', 2)">Si instalo más, el caos me arruina el margen</div>
        </div>

        <div class="quiz-step" id="step2">
            <p class="question-text">> LA ESTRATEGIA DE 168 HORAS:</p>
            <div class="vsl-box">
                <p style="color:var(--accent); font-size:0.7rem; margin-bottom:10px;">[ DECODIFICANDO SOLUCIÓN INTEGRAL ]</p>
                <div style="height: 180px; display:flex; align-items:center; justify-content:center; color:#444;">VÍDEO DE BUNNY.NET CARGANDO...</div>
            </div>
            <div class="option-card" onclick="select(2, 'SISTEMA_LLAVE_MANO', 3)">SÍ, QUIERO ESTA INFRAESTRUCTURA YA</div>
            <span class="nav-link" onclick="go(1)">[ VOLVER ]</span>
        </div>

        <div class="quiz-step" id="step3">
            <p class="question-text">> CREDENCIALES PARA AUDITORÍA 10X:</p>
            <form onsubmit="finish(event)">
                <input type="text" id="name" class="form-input" placeholder="TU NOMBRE (CEO)" required>
                <input type="text" id="company" class="form-input" placeholder="EMPRESA INSTALADORA" required>
                <input type="tel" id="phone" class="form-input" placeholder="WHATSAPP PERSONAL" required>
                <button type="submit" class="submit-btn">ACTIVAR PROTOCOLO GARANTIZADO</button>
            </form>
            <span class="nav-link" onclick="go(2)">[ VOLVER ]</span>
        </div>
    </div>

    <script>
        let results = { p1: '', p2: '' };
        const WEBHOOK = 'https://n8n.planneruniversedigital.com/webhook-test/539d7879-37ff-47a1-a64e-6186a94aa0f8';
        const WHATSAPP = '346XXXXXXXX'; // TU TELÉFONO AQUÍ

        function select(step, val, next) {
            results['p' + step] = val;
            go(next);
        }

        function go(s) {
            document.querySelectorAll('.quiz-step').forEach(el => el.classList.remove('active'));
            document.getElementById('step' + s).classList.add('active');
            document.getElementById('bar').style.width = (s * 33) + '%';
        }

        async function finish(e) {
            e.preventDefault();
            const n = document.getElementById('name').value;
            const c = document.getElementById('company').value;
            const p = document.getElementById('phone').value;

            const finalData = { ...results, nombre: n, empresa: c, tel: p };

            // Disparo a n8n
            fetch(WEBHOOK, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(finalData) });

            // Cierre en WhatsApp
            const text = `César, soy ${n} de ${c}. Mi beneficio es bajo por ${results.p1}. He visto el vídeo y quiero el sistema llave en mano en 7 días. ¡Fuego!`;
            window.location.href = `https://wa.me/${WHATSAPP}?text=${encodeURIComponent(text)}`;
        }
    </script>
</body>
</html>

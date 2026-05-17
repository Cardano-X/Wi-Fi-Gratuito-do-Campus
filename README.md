<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal de Autenticação Wi-Fi</title>
    <style>
        :root {
            --primary-color: #0066cc;
            --background-color: #f0f2f5;
            --card-background: #ffffff;
            --text-color: #333333;
        }
        
        body { 
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif; 
            text-align: center; 
            padding: 40px 20px; 
            background-color: var(--background-color); 
            color: var(--text-color);
            margin: 0;
        }
        
        .logo-container {
            margin-bottom: 25px;
        }

        .wifi-icon {
            font-size: 48px;
            color: var(--primary-color);
        }

        h1.main-title { 
            color: var(--primary-color); 
            font-size: 1.8rem; 
            margin: 10px 0 30px 0;
            font-weight: 600;
        }
        
        .box { 
            background: var(--card-background); 
            padding: 40px 30px; 
            border-radius: 12px; 
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05); 
            display: inline-block; 
            max-width: 420px; 
            width: 100%; 
            box-sizing: border-box;
            text-align: left;
        }

        .box h2 {
            margin-top: 0;
            font-size: 1.4rem;
            color: #111;
        }

        .box p {
            color: #666;
            font-size: 0.95rem;
            line-height: 1.5;
            margin-bottom: 25px;
        }
        
        .input-group {
            margin-bottom: 15px;
        }

        .input-group label {
            display: block;
            margin-bottom: 6px;
            font-size: 0.85rem;
            font-weight: 600;
            color: #555;
        }

        input { 
            width: 100%; 
            padding: 12px; 
            border: 1px solid #cccccc; 
            border-radius: 6px; 
            box-sizing: border-box;
            font-size: 1rem;
            transition: border-color 0.2s;
        }

        input:focus {
            outline: none;
            border-color: var(--primary-color);
        }
        
        button { 
            background-color: var(--primary-color); 
            color: white; 
            border: none; 
            padding: 14px; 
            border-radius: 6px; 
            cursor: pointer; 
            width: 100%; 
            font-size: 1rem; 
            font-weight: 600;
            margin-top: 10px;
            transition: background-color 0.2s;
        }

        button:hover {
            background-color: #0052a3;
        }
        
        /* Telas de transição secundárias */
        .step-page { display: none; }

        .download-btn {
            background-color: #28a745;
            text-decoration: none;
            color: white;
            display: block;
            text-align: center;
            padding: 14px;
            border-radius: 6px;
            font-weight: 600;
            margin-top: 20px;
        }

        .download-btn:hover {
            background-color: #218838;
        }

        /* Alerta Educativo Final */
        .alert-box { 
            display: none; 
            background-color: #fff5f5; 
            border-left: 6px solid #e53e3e; 
            padding: 30px; 
            color: #2d3748; 
            margin: 20px auto; 
            text-align: left; 
            max-width: 500px; 
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
        }

        .alert-box h3 { color: #c53030; margin-top: 0; font-size: 1.3rem; }
        .alert-box hr { border: 0; border-top: 1px solid #fed7d7; margin: 20px 0; }
        .alert-box ul { padding-left: 20px; line-height: 1.6; }
        .alert-box li { margin-bottom: 10px; }
    </style>
</head>
<body>

<div class="logo-container">
    <div class="wifi-icon">📶</div>
    <h1 class="main-title">Wi-Fi Corporativo Campus</h1>
</div>

<div class="box step-page" id="step1" style="display: inline-block;">
    <h2>Autenticação de Usuário</h2>
    <p>Para acessar a rede sem fio gratuita do campus, valide sua identidade com as credenciais acadêmicas.</p>
    
    <div class="input-group">
        <label for="email">E-mail Institucional</label>
        <input type="email" id="email" placeholder="nome.sobrenome@instituicao.edu.br" required>
    </div>
    
    <div class="input-group">
        <label for="password">Senha de Acesso</label>
        <input type="password" id="password" placeholder="••••••••" required>
    </div>
    
    <button onclick="irParaPasso2()">Acessar Internet</button>
</div>

<div class="box step-page" id="step2">
    <h2>Conexão Quase Concluída!</h2>
    <p>Para garantir a segurança dos seus dados e a estabilidade da navegação, é necessário instalar o <strong>Certificado de Conexão Acadêmica</strong> no seu dispositivo.</p>
    
    <div style="background: #f7fafc; padding: 15px; border-radius: 6px; border: 1px solid #e2e8f0; font-size: 0.9rem; color: #4a5568;">
        <strong>Arquivo:</strong> Certificado_WiFi_Campus.apk<br>
        <strong>Compatibilidade:</strong> Android 8.0 ou superior
    </div>

    <a href="#" class="download-btn" onclick="mostrarAlertaEducativo(event)">Baixar Certificado e Conectar</a>
</div>

<div class="alert-box" id="finalAlert">
    <h3>⚠️ Demonstração de Segurança Cibernética</h3>
    <p><strong>Isto é um ambiente controlado para fins educacionais.</strong></p>
    <p>Nenhum dado foi coletado e nenhum arquivo malicioso foi transferido para o seu dispositivo.</p>
    
    <hr>
    
    <p><strong>Análise Técnica do Vetor de Ataque (Qshing):</strong></p>
    <ul>
        <li><strong>Fase 1 (Roubo de Credenciais):</strong> A página simula perfeitamente a identidade visual de um portal legítimo. Usuários desatentos inserem dados sem validar o domínio na barra de endereços.</li>
        <li><strong>Fase 2 (Tentativa de Infecção):</strong> Ao clicar para "Baixar o Certificado", o atacante enviaria um aplicativo modificado (malware). </li>
        <li><strong>O Fator Crítico:</strong> Para obter o controle do celular, o invasor depende de duas ações adicionais da vítima: que ela ignore o aviso do sistema sobre "Fontes Desconhecidas" e conceda permissões críticas (como os <em>Serviços de Acessibilidade</em>).</li>
    </ul>
</div>

<script>
    function irParaPasso2() {
        // Validação simples apenas para fins de navegação no slide
        var email = document.getElementById('email').value;
        var pass = document.getElementById('password').value;
        
        if(email !== "" && pass !== "") {
            document.getElementById('step1').style.display = 'none';
            document.getElementById('step2').style.display = 'inline-block';
        } else {
            alert("Por favor, preencha os campos para simular o acesso.");
        }
    }

    function mostrarAlertaEducativo(event) {
        event.preventDefault(); // Impede qualquer navegação ou download real
        document.getElementById('step2').style.display = 'none';
        
        // Esconde a estrutura do cabeçalho original para focar no alerta
        document.querySelector('.logo-container').style.display = 'none';
        
        document.getElementById('finalAlert').style.display = 'block';
    }
</script>

</body>
</html>

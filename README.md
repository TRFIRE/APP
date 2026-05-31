🚒 TR FIRE App - Sistema de Inspeções e Rondas

O TR FIRE é um aplicativo Web (PWA) focado no controle, inspeção preventiva e auditoria de equipamentos de segurança contra incêndio e rondas operacionais.

Desenvolvido com uma arquitetura moderna de Arquivo Único (Single-File), todo o sistema (Interface, Lógica e Banco de Dados) roda a partir de um único arquivo index.html, permitindo facilidade extrema de hospedagem e manutenção.

✨ Principais Funcionalidades

🔍 Módulos de Inspeção

🧯 Extintores: Controle de lacre, obstrução, sinalização, vencimento de recarga e teste hidrostático.

🚰 Hidrantes: Verificação de integridade, desobstrução, lacres e teste hidrostático.

🚿 VGA (SPK): Validação de placas, válvulas, vazamentos, chave de fluxo, danos mecânicos e manômetros.

🚶‍♂️ Rondas Diárias: Controle rigoroso de rondas por turnos (Diurno e Noturno) em locais predefinidos, com sistema de "trava de horário" e alertas de atraso.

⚙️ Recursos Técnicos

📷 Leitor de QR Code Integrado: Escaneamento ágil de equipamentos diretamente pela câmera do celular utilizando a biblioteca html5-qrcode.

📸 Registro Fotográfico Otimizado: Captura de fotos como evidência, com compressão inteligente nativa (via <canvas>) antes do envio ao banco de dados para economizar espaço de armazenamento.

📶 Modo Offline: Capacidade de realizar inspeções sem internet. Os dados ficam salvos no cache do navegador e são sincronizados automaticamente assim que a conexão é restabelecida (via Firebase Persistence).

📄 Geração de Relatórios PDF: Criação de relatórios analíticos em tabelas e relatórios fotográficos diretamente no dispositivo do usuário (Client-side) usando jsPDF.

🗑️ Lixeira e Retenção: Sistema de "Soft Delete", permitindo restauração de inspeções apagadas e limpeza automática após 72 horas.

🤖 Auditoria Automática: O sistema gera "faltas" automáticas (Inspeção Não Realizada) se um local de ronda for esquecido durante o turno pela equipe operacional.

🛡️ Gestão e Administração

Painel completo de Parâmetros Admin exclusivo para Gestores (ADMIN, SUPERVISOR, COORDENADOR), contendo:

Controle de Acesso e Permissões por usuário.

Gestão de Unidades e Turnos.

Gerenciamento Dinâmico de Locais e Sublocais (com edição em cascata).

Gestão da Equipe de Bombeiros.

Exportação e Importação de dados (Backup em .json).

💻 Tecnologias Utilizadas

O projeto foi construído para não depender de processos de build no servidor (como Webpack ou Vite), compilando tudo em tempo de execução através de CDNs:

React 18 (via CDN + Babel Standalone para JSX)

Tailwind CSS (via script CDN para estilização rápida e responsiva)

Firebase Firestore & Auth (Compat v10) (Banco de dados em tempo real e Autenticação Anônima/Sessão)

jsPDF & autoTable (Geração de documentos PDF)

Html5-Qrcode (Leitura de códigos de barra e QR)

FontAwesome (Ícones da interface)

Ícones SVG Customizados (Hidrantes e SPK criados diretamente no código)

🚀 Como Executar / Hospedar (GitHub Pages)

Por ser uma aplicação baseada no front-end, o deploy é extremamente simples e gratuito.

Crie um repositório no GitHub.

Faça o upload do arquivo principal index.html.

Faça o upload da logomarca do sistema nomeada exatamente como logo.png na mesma pasta. (Se não houver logo, o app exibirá um ícone de extintor como fallback).

Acesse as Settings (Configurações) do seu repositório no GitHub.

Vá até a aba Pages.

Na seção "Build and deployment", selecione a branch main (ou master) e clique em Save.

Pronto! Em alguns minutos o GitHub fornecerá um link público seguro (HTTPS) para você acessar o TR FIRE de qualquer celular ou computador.

Nota: Não é necessário adicionar um arquivo .nojekyll pois o projeto não possui pastas que iniciam com sublinhado (_).

🔒 Segurança e Banco de Dados (Firebase)

As credenciais do Firebase (apiKey, projectId, etc) estão expostas no código, o que é um comportamento padrão em aplicações Client-side / SPA.

A segurança real e proteção contra acessos indevidos deve ser garantida através das Regras de Segurança (Security Rules) diretamente no console do Firebase Firestore, garantindo que apenas a sua conta de serviço ou usuários logados possam ler/escrever na coleção inspections, users e main_locations.

Desenvolvido por: Thawillys Rocha / Fire Personality ME
Versão Atual: Mestre V89.2
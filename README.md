execute o seguinte site: <!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ficha de Pré Atendimento</title>
    <!-- Inclui o CDN do Tailwind CSS para estilização -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Define a fonte Inter para todo o corpo, com fallback */
        body {
            font-family: "Inter", sans-serif;
        }
        /* Estilos personalizados para o textarea para garantir que ele preencha a largura */
        textarea {
            resize: vertical; /* Permite redimensionar verticalmente */
        }
        /* Esconde o modal por padrão */
        .modal {
            display: none;
        }
        /* Estilo para o backdrop do modal */
        .modal-backdrop {
            background-color: rgba(0, 0, 0, 0.5);
        }
    </style>
</head>
<body class="bg-gray-100 p-4 flex justify-center items-center min-h-screen">
    <div class="container bg-white p-6 md:p-8 rounded-lg shadow-lg w-full max-w-4xl">
        <h1 class="text-3xl font-bold text-center text-blue-700 mb-6">FICHA DE PRÉ ATENDIMENTO</h1>

        <!-- O atributo 'action' do formulário será atualizado com o endpoint do Formspree -->
        <!-- Substitua 'YOUR_FORMSPREE_FORM_ID' pelo ID que você obterá no Formspree -->
        <form id="attendanceForm" class="space-y-6" action="https://formspree.io/f/mblkgwej">
            <!-- Seção de Dados do Cliente -->
            <section class="border-b pb-4 border-gray-200">
                <h2 class="text-2xl font-semibold text-blue-600 mb-4">Dados do Cliente</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="form-group">
                        <label for="nome" class="block text-gray-700 font-medium mb-1">Nome:</label>
                        <input type="text" id="nome" name="Nome" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500" required>
                    </div>
                    <div class="form-group">
                        <label for="endereco" class="block text-gray-700 font-medium mb-1">Endereço:</label>
                        <input type="text" id="endereco" name="Endereço" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500" required>
                    </div>
                    <div class="form-group">
                        <label for="telefone" class="block text-gray-700 font-medium mb-1">Telefone:</label>
                        <input type="tel" id="telefone" name="Telefone" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500" required>
                    </div>
                    <div class="form-group">
                        <label for="email" class="block text-gray-700 font-medium mb-1">E-mail:</label>
                        <input type="email" id="email" name="Email" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500" required>
                    </div>
                </div>
            </section>

            <!-- Seção de Questionário -->
            <section class="border-b pb-4 border-gray-200">
                <h2 class="text-2xl font-semibold text-blue-600 mb-4 mt-6">Questionário</h2>
                <div class="space-y-4">
                    <div class="form-group">
                        <label for="q1" class="block text-gray-700 font-medium mb-1">1) Qual a data do falecimento?</label>
                        <input type="date" id="q1" name="1_Data_Falecimento" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500">
                    </div>
                    <div class="form-group">
                        <label for="q2" class="block text-gray-700 font-medium mb-1">2) O falecido era casado ou vivia em união estável? Qual o regime de bens?</label>
                        <textarea id="q2" name="2_Estado_Civil_Regime_Bens" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q3" class="block text-gray-700 font-medium mb-1">3) Quais os bens deixados em nome do falecido?</label>
                        <textarea id="q3" name="3_Bens_Falecido" rows="3" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q4" class="block text-gray-700 font-medium mb-1">4) Há algum bem com irregularidade? Por exemplo, em nome de terceiro?</label>
                        <textarea id="q4" name="4_Bens_Irregularidade" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q5" class="block text-gray-700 font-medium mb-1">5) Quando os bens foram adquiridos e com quais recursos?</label>
                        <textarea id="q5" name="5_Aquisicao_Bens" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q6" class="block text-gray-700 font-medium mb-1">6) O cônjuge ou companheiro possui bens? Quando houve a aquisição e qual a origem do recurso?</label>
                        <textarea id="q6" name="6_Bens_Conjugue" rows="3" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q7" class="block text-gray-700 font-medium mb-1">7) Algum herdeiro é pré-morto?</label>
                        <textarea id="q7" name="7_Herdeiro_Pre_Morto" rows="1" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q8" class="block text-gray-700 font-medium mb-1">8) Houve antecipação de herança (doação ou compra e venda sem anuência)?</label>
                        <textarea id="q8" name="8_Antecipacao_Heranca" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q9" class="block text-gray-700 font-medium mb-1">9) Há dívidas em nome do falecido? Essas dívidas foram contraídas em benefício da família?</label>
                        <textarea id="q9" name="9_Dividas_Falecido" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q10" class="block text-gray-700 font-medium mb-1">10) Há dívidas em nome do cônjuge ou companheiro? Essas dívidas foram contraídas em benefício da família?</label>
                        <textarea id="q10" name="10_Dividas_Conjugue" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q11" class="block text-gray-700 font-medium mb-1">11) Há saldos bancários, aplicações, investimentos em nome do falecido?</label>
                        <textarea id="q11" name="11_Saldos_Falecido" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q12" class="block text-gray-700 font-medium mb-1">12) Há saldos bancários, aplicações, investimentos em nome do cônjuge sobrevivente?</label>
                        <textarea id="q12" name="12_Saldos_Conjugue" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q13" class="block text-gray-700 font-medium mb-1">13) Há ações em trâmite em que o falecido ou cônjuge/companheiro figura como autor ou réu?</label>
                        <textarea id="q13" name="13_Acoes_Tramite" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q14" class="block text-gray-700 font-medium mb-1">14) Há algum herdeiro incapaz?</label>
                        <textarea id="q14" name="14_Herdeiro_Incapaz" rows="1" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q15" class="block text-gray-700 font-medium mb-1">15) Há litígio entre os herdeiros? Se sim, qual o motivo?</label>
                        <textarea id="q15" name="15_Litigio_Herdeiros" rows="2" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q16" class="block text-gray-700 font-medium mb-1">16) Haveria possibilidade de acordo?</label>
                        <textarea id="q16" name="16_Possibilidade_Acordo" rows="1" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q17" class="block text-gray-700 font-medium mb-1">17) Sabe da existência de seguro de vida deixado pelo falecido?</label>
                        <textarea id="q17" name="17_Seguro_Vida" rows="1" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                    <div class="form-group">
                        <label for="q18" class="block text-gray-700 font-medium mb-1">18) Há recurso financeiro para pagamento do ITCD?</label>
                        <textarea id="q18" name="18_Recurso_ITCD" rows="1" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                    </div>
                </div>
            </section>

            <!-- Seção de Dúvidas e Anotações -->
            <section class="space-y-4">
                <div class="form-group">
                    <label for="duvidasCliente" class="block text-gray-700 font-medium mb-1">Dúvidas do cliente:</label>
                    <textarea id="duvidasCliente" name="Duvidas_Cliente" rows="10" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                </div>
                <div class="form-group">
                    <label for="anotacoesAtendimento" class="block text-gray-700 font-medium mb-1">Anotações sobre o atendimento:</label>
                    <textarea id="anotacoesAtendimento" name="Anotacoes_Atendimento" rows="10" class="w-full p-2 border border-gray-300 rounded-md focus:ring-blue-500 focus:border-blue-500"></textarea>
                </div>
            </section>

            <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded-md transition duration-300 ease-in-out shadow-md">
                Enviar Ficha
            </button>
        </form>

        <!-- Área para exibir os resultados do formulário (agora apenas para feedback visual) -->
        <div id="results" class="mt-8 p-6 bg-gray-50 border border-gray-200 rounded-lg hidden">
            <h2 class="text-2xl font-semibold text-blue-600 mb-4">Dados Enviados (para visualização):</h2>
            <pre id="resultsContent" class="whitespace-pre-wrap font-mono text-sm text-gray-800 bg-gray-100 p-4 rounded-md"></pre>
        </div>
    </div>

    <!-- Modal para mensagens -->
    <div id="messageModal" class="modal fixed inset-0 flex items-center justify-center z-50">
        <div class="modal-backdrop absolute inset-0"></div>
        <div class="modal-content bg-white p-6 rounded-lg shadow-xl z-10 max-w-sm w-full">
            <h3 class="text-xl font-bold mb-4" id="modalTitle"></h3>
            <p class="text-gray-700 mb-6" id="modalMessage"></p>
            <button id="closeModal" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-md transition duration-300 ease-in-out">
                OK
            </button>
        </div>
    </div>

    <script>
        // Aguarda o carregamento completo do DOM
        document.addEventListener('DOMContentLoaded', () => {
            // Obtém referências para o formulário e a área de resultados
            const form = document.getElementById('attendanceForm');
            const resultsDiv = document.getElementById('results');
            const resultsContent = document.getElementById('resultsContent');
            const messageModal = document.getElementById('messageModal');
            const modalTitle = document.getElementById('modalTitle');
            const modalMessage = document.getElementById('modalMessage');
            const closeModalButton = document.getElementById('closeModal');

            // Função para exibir o modal de mensagem
            function showModal(title, message) {
                modalTitle.textContent = title;
                modalMessage.textContent = message;
                messageModal.classList.remove('hidden');
                messageModal.classList.add('flex'); // Garante que o modal seja exibido com flex
            }

            // Função para fechar o modal de mensagem
            closeModalButton.addEventListener('click', () => {
                messageModal.classList.add('hidden');
                messageModal.classList.remove('flex');
            });

            // Adiciona um listener para o evento de submit do formulário
            form.addEventListener('submit', async (event) => {
                event.preventDefault(); // Previne o comportamento padrão de recarregar a página

                // Exibe uma mensagem de carregamento
                showModal('Enviando...', 'Por favor, aguarde enquanto a ficha é enviada.');

                // Cria um objeto FormData a partir do formulário
                const formData = new FormData(form);
                const data = {};

                // Itera sobre os dados do formulário e os armazena em um objeto JavaScript
                for (let [key, value] of formData.entries()) {
                    data[key] = value;
                }

                try {
                    // Envia os dados para o Formspree usando fetch
                    const response = await fetch(form.action, {
                        method: form.method,
                        body: formData, // Envia FormData diretamente para Formspree
                        headers: {
                            'Accept': 'application/json' // Indica que esperamos JSON como resposta
                        }
                    });

                    if (response.ok) { // Verifica se a resposta foi bem-sucedida (status 2xx)
                        // Exibe os dados coletados na área de resultados na página para visualização
                        resultsContent.textContent = JSON.stringify(data, null, 2); // Formata o JSON para leitura
                        resultsDiv.classList.remove('hidden'); // Torna a área de resultados visível

                        showModal('Ficha Enviada!', 'Sua ficha foi enviada com sucesso!');
                        form.reset(); // Limpa o formulário após o envio bem-sucedido
                    } else {
                        // Tenta ler a mensagem de erro da resposta, se disponível
                        const errorData = await response.json();
                        showModal('Erro no Envio!', `Ocorreu um erro ao enviar a ficha: ${errorData.error || response.statusText}.`);
                    }
                } catch (error) {
                    console.error('Erro ao enviar o formulário:', error);
                    showModal('Erro de Conexão!', 'Não foi possível conectar ao servidor. Verifique sua conexão com a internet.');
                }
            });
        });
    </script>
</body>
</html>

Processador de Parcelas
Aplicação Streamlit para gestão de parcelas de empréstimos. Processa planilhas Excel, atualiza automaticamente o número de parcelas e gera relatórios de parcelas quitadas com formato profissional.

✨ Funcionalidades
Dois modos de processamento – adequados para diferentes estruturas de planilha.

Atualização automática – incrementa o número total de parcelas quando uma nova parcela é paga.

Identificação de quitados – oculta linhas quitadas e gera relatório separado.

Relatório profissional – formatação automática com cabeçalhos, cores alternadas, bordas e cabeçalho fixo para impressão.

Interface moderna – design responsivo e intuitivo, pronto para uso no navegador.

📋 Requisitos
Python 3.8 ou superior

Navegador web (Chrome, Firefox, Edge, etc.)

🚀 Instalação
Clone o repositório (ou baixe o arquivo):

bash
git clone https://github.com/seu-usuario/mv-contabilidade.git
cd mv-contabilidade
Crie um ambiente virtual (opcional, mas recomendado):

bash
python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows
Instale as dependências:

bash
pip install streamlit pandas openpyxl
Execute a aplicação:

bash
streamlit run app.py
A aplicação abrirá automaticamente no seu navegador.

🧩 Estrutura da Planilha
A planilha de entrada deve estar no formato .xlsx com uma única aba (a primeira é utilizada).

Modo 1: Empréstimos Individuais
Utiliza a coluna H (células com o formato (X/Y), ex: (3/12)).

Funcionamento:
Quando X == Y, a linha é considerada quitada → oculta na planilha atual e copiada para o relatório de quitados.
Caso contrário, a célula é atualizada para (X/Y+1), incrementando o total de parcelas.

Modo 2: Empréstimos
Utiliza as colunas D (parcela atual) e F (total de parcelas).

Funcionamento:
O valor da coluna F é incrementado em 1.
Se após o incremento F == D, a linha é considerada quitada → oculta e copiada para o relatório.
Em qualquer caso, a coluna F é atualizada com o novo total.

📂 Arquivos Gerados
Após o processamento, são gerados dois arquivos no mesmo diretório da planilha original:

{nome}_ATUALIZADO_{mes}_{ano}.xlsx – Planilha original com as linhas quitadas ocultas e os valores atualizados (coluna H ou F).

{nome}_QUITADOS_{mes}_{ano}.xlsx – Relatório contendo apenas as linhas quitadas, com formatação profissional, cabeçalho fixo e autofiltro.

🖥️ Como Usar
Acesse a aplicação no navegador.

Escolha a aba correspondente ao formato da sua planilha:

Empréstimos Individuais – para planilhas com coluna H no formato (X/Y).

Empréstimos – para planilhas com colunas D e F contendo números de parcelas.

Arraste ou selecione o arquivo .xlsx.

Informe o mês e o ano de referência (usados para nomear os arquivos e no cabeçalho do relatório).

Clique em Processar.

Aguarde o processamento e baixe os arquivos gerados.

🎨 Estilo e Impressão
O relatório de quitados é formatado para impressão:

Cabeçalho fixo (repetido em cada página)

Orientação paisagem

Ajuste automático de largura das colunas

Cores suaves e bordas

Autofiltro nas colunas de dados

⚙️ Personalização
Você pode ajustar o código para:

Alterar as colunas utilizadas (ex: coluna H para outra letra)

Modificar o formato do relatório (cores, fontes, etc.)

Adicionar mais colunas ao relatório (a aplicação já detecta colunas não vazias)

🐛 Solução de Problemas
Erro ao carregar arquivo: Certifique-se de que o arquivo é .xlsx e não está corrompido.

Arquivos não aparecem no diretório: Os arquivos são salvos no mesmo local da planilha original. Verifique se você tem permissão de escrita.

Nenhuma parcela quitada: Se a planilha não contém dados compatíveis, o relatório será gerado vazio, mas a planilha atualizada ainda será criada.

📄 Licença
Este projeto é distribuído sob a licença MIT. Sinta-se à vontade para usar, modificar e compartilhar.


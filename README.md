HappyPaws - Integrando dados de saúde e atividades 🐾
Este projeto nasceu de uma necessidade real da HappyPaws: unificar a base de dados do aplicativo deles. O time de engenharia perdia muito tempo cruzando fontes diferentes, então eu criei um pipeline em Python para consolidar tudo em uma "Single Source of Truth".

O Problema
Eu tinha três arquivos CSV bem distintos nas mãos: logs de atividades diárias, registros de visitas ao veterinário e o cadastro dos donos. O desafio não era só juntar tudo, mas limpar as inconsistências e garantir que o resultado final fosse útil para o time de desenvolvimento.

O que eu resolvi no código:
Unificação de eventos: Padronizei os registros para que atividades (caminhadas, brincadeiras) e visitas médicas coexistissem na mesma linha do tempo.

Limpeza "na mão": Removi espaços extras em colunas de texto e corrigi categorias que vinham zumbadas nos CSVs.

Tratamento de tipos: Garanti que as datas fossem objetos datetime reais e não apenas texto, além de forçar durações zeradas para consultas médicas, conforme a regra de negócio.

Integridade: O código barra registros sem ID do pet ou sem data, evitando que dados "fantasmas" poluam o DataFrame final.

Stack utilizada
Basicamente usei Python com Pandas e NumPy, focando em eficiência e código limpo.

Como rodar
A lógica principal está na função all_pet_data. É só passar os três caminhos dos arquivos e ela te entrega o DataFrame pronto para o deploy.
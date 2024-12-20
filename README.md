# Meu Projeto
Projeto: Treinamento de Rede YOLO para Detecção de Objetos

Introdução

Este projeto implementa o treinamento da rede YOLO para detecção de objetos em imagens. Ele inclui a criação de uma base de dados, rotulação de imagens, geração de arquivos de configuração e treinamento usando o framework Darknet.

Ferramentas Utilizadas

LabelMe: Ferramenta para rotulação de imagens. Acesse o LabelMe

YOLO (Darknet): Framework para detecção de objetos. Mais informações sobre YOLO

Google Colab (Opcional): Para quem não possui recursos locais para o treinamento. Acesse o notebook.

Estrutura do Projeto

dataset/: Contém as imagens e arquivos de rótulo.

images/: Imagens de treino e validação.

labels/: Arquivos de rótulo no formato YOLO.

obj.names: Arquivo com os nomes das classes.

obj.data: Configuração do dataset para o Darknet.

train.txt: Lista de imagens de treinamento.

val.txt: Lista de imagens de validação.

backup/: Diretório para salvar os pesos treinados.

Como Usar

1. Configurar o Ambiente

Clone o repositório Darknet e compile:

git clone https://github.com/AlexeyAB/darknet.git
cd darknet
make

Instale o LabelMe para rotular as imagens:

pip install labelme

2. Preparar o Dataset

Rotule as imagens:
Use o LabelMe para criar os rótulos e exporte no formato YOLO.

Organize o diretório:
Estruture suas imagens e rótulos no diretório dataset/ conforme descrito acima.

Gere os arquivos de configuração:
O script yolo_training_project.py automatiza a criação de obj.names, obj.data, train.txt e val.txt.

3. Configurar o YOLO

Edite o arquivo yolov3.cfg para ajustar:

classes: Defina o número total de classes no dataset.

filters: Ajuste para (classes + 5) * 3 na penúltima camada da rede.

4. Iniciar o Treinamento

Baixe os pesos pré-treinados:

wget https://pjreddie.com/media/files/darknet53.conv.74

Execute o treinamento:

./darknet detector train obj.data yolov3.cfg darknet53.conv.74

Para usar o Google Colab, carregue seu dataset e ajuste o notebook fornecido.

5. Testar o Modelo Treinado

Teste a detecção em uma imagem:

./darknet detector test obj.data yolov3.cfg yolov3_last.weights imagem.jpg

Os resultados serão exibidos no terminal e a imagem processada será salva.

Resultados

Inclua os resultados obtidos com o modelo treinado, como imagens de exemplo e métricas (exemplo: mAP).

Considerações Finais

Este projeto pode ser adaptado para diferentes aplicações de detecção de objetos. Ele oferece um ponto de partida para treinar a rede YOLO com dados personalizados. Caso tenha dúvidas ou sugestões, entre em contato!


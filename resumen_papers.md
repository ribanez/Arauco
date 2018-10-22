# RESUMEN PAPERS

## Arquitecturas para el procesamiento de datos Secuenciales

#### Learning Longer-term Dependencies in RNNs with Auxiliary Losses [arxiv:1803.00144](https://arxiv.org/abs/1803.00144)

Se propone el uso de perdidas auxiliares no supervisadas por la perdida principal que permita reconstruir/predecir un segmento aleatorio de la secuencia antes o despues de un punto de anclaje, esto permite hacer truncate backpropagation (TTBP) unos pocos pasos desde la pérdida supervisada lo cual disminuye los costos de las redes recurrentes sin perdida en las dependencias de largo alcance. Un esquema principal de este paper se muestra en la siguiente figura.

<img src="./Images/Aux_loss1.jpg" width="200"/> 

Se proponen dos tipos de perdidas auxiliares, la reconstrucción y la predicción.

1) La perdida auxiliar mediante reconstruccion consiste en intentar reconstruir una subsecuencia anterior al punto de anclaje mediante un modelo de encoder-decoder regresivo, a este modelo se le llama rLSTM. Esto se puede apreciar en la siguiente figura.

<img src="./Images/Aux_loss2.jpg" width="200"/> 

2) La perdida auxiliar de predicción consiste en predecir los siguientes pasos de la secuencia posteriores a un punto de anclaje, a este modelo se le llama pLSTM. Esto se puede apreciar en la siguiente figura.

<img src="./Images/Aux_loss3.jpg" width="200"/> 

Los modelos se sometieron a pruebas de estrés de memoria y a tareas de lenguaje comparando la performance con LSTM full BP, con LSTM Truncate BP truncando en 300 steps y Transformer.

Los resultados muestran que tiene en ciertos dataset presenta ventajas sustanciales, mientras que en otros se si bien no mejora, el costo computacional del entrenamiento es considerablemente menor.

Tabla 1: Test accuracy (%)

|                   | MNIST | pMNIST | CIFAR10 |
|-------------------|-------|--------|---------|
| LSTM Full BP      | 98.3  | 89.4   | 58.8    |
| LSTM Truncate300  | 11.3  | 88.8   | 49.0    |
| Transformer       | 98.9  | 97.9   | 62.2    |
| rLSTM Truncate300 | 96.4  | 92.8   | 65.9    |
| pLSTM Truncate300 | 95.4  | 92.5   | 64.7    |
| rLSTM Full BP     | 98.4  | 95.2   | 72.2    |
| pLSTM Full BP     | 98.0  | 92.8   | 67.6    |

#### Nested LSTMs [arxiv:1801.10308](https://arxiv.org/abs/1801.10308)

#### WaveNet: A Generative Model for Raw Audio [arxiv:1609.03499](https://arxiv.org/abs/1609.03499)

#### An Empirical Evaluation of Generic Convolutional and Recurrent Networks for Sequence Modelling [arxiv:1803.01271](https://arxiv.org/abs/1803.01271)

#### Trellis Networks for Sequence Modeling [arxiv:1810.06682](https://arxiv.org/abs/1810.06682)


## Arquitecturas para Reinforcement Learning

#### Configurable Markov Processes [arxiv:1806.05415](https://arxiv.org/abs/1806.05415)

#### On improving Deep Reinforcement Learning for POMDPs [arxiv:1704.07978](https://arxiv.org/abs/1704.07978)
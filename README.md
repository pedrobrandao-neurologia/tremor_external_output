```markdown
# TremorPSD - Análise de Tremor por Densidade Espectral de Potência

## Visão Geral

TremorPSD é uma aplicação web progressiva para análise quantitativa de tremores usando os sensores de movimento do dispositivo ou arquivos externos. O sistema processa sinais de acelerometria e calcula métricas espectrais avançadas para auxiliar na caracterização de diferentes tipos de tremor.

## Funcionalidades Principais

### 📊 Análise Espectral
- **Método de Welch** para cálculo robusto da Densidade Espectral de Potência (PSD)
- Detecção automática da frequência dominante do tremor (2-20 Hz)
- Visualização em tempo real do sinal e do espectro de frequências

### 📈 Métricas Calculadas
- **Frequência de Pico**: Frequência dominante do tremor em Hz
- **Amplitude (RMS)**: Intensidade do tremor no domínio do tempo
- **Potência Total**: Energia total do sinal
- **Proeminência do Pico**: Distinção do pico principal vs ruído de fundo
- **FWHM (Full Width at Half Maximum)**: Largura espectral do pico
- **TSI (Tremor Stability Index)**: Índice de estabilidade/regularidade
- **Entropia Espectral**: Complexidade do sinal
- **Jerk (JR50)**: Mediana da derivada da aceleração (suavidade do movimento)
- **Índice Wavelet**: Consistência temporal do tremor na frequência dominante

### 🎯 Classificação Sugerida
Sistema de pontuação probabilística para diferentes tipos de tremor:
- **Tremor Ortostático** (13-18 Hz)
- **Tremor Essencial** (4-12 Hz)
- **Tremor Distônico** (irregular, 3-9 Hz)
- **Mioclonia** (movimentos súbitos)

### 📱 Fontes de Dados
1. **Acelerômetro do Dispositivo**: Coleta direta usando sensores do smartphone/tablet
2. **Arquivo Externo**: Importação de dados TXT/CSV com suporte para:
   - Formatos Spike2/SMR exportados
   - CSV com colunas tempo/x/y/z
   - Detecção automática da taxa de amostragem

### 💾 Exportação
- **PDF**: Relatório completo com gráficos e interpretação das métricas
- **CSV de Métricas**: Todas as métricas calculadas em formato tabular
- **CSV de Dados Brutos**: Série temporal original para reanálise

## Requisitos Técnicos

### Para Uso com Sensores
- Navegador com suporte a DeviceMotionEvent API
- Conexão HTTPS ou localhost (requisito de segurança do navegador)
- Dispositivo com acelerômetro (smartphone/tablet)

### Para Análise de Arquivos
- Qualquer navegador moderno
- Arquivos TXT ou CSV com dados de acelerometria

## Como Usar

### Modo Sensor
1. Acesse a aplicação em HTTPS ou localhost
2. Conceda permissão para usar os sensores
3. Configure duração (5-60s) e eixo de análise
4. Clique em "Iniciar Coleta"
5. Mantenha o dispositivo ou a parte do corpo com tremor
6. Aguarde análise automática ao fim da coleta

### Modo Arquivo
1. Selecione "Arquivo externo" como fonte de dados
2. Configure a taxa de amostragem (ou use a detectada automaticamente)
3. Carregue arquivo TXT/CSV
4. Clique em "Analisar Arquivo"

## Base Científica

O sistema utiliza técnicas estabelecidas de processamento de sinais biomédicos:

- **Remoção de Tendência**: Elimina componente DC do sinal
- **FFT com Janelamento**: Transformada de Fourier com janela de Hanning
- **Método de Welch**: Média de periodogramas com sobreposição de 50%
- **Análise Wavelet**: Wavelets de Morlet para análise tempo-frequência
- **Métricas de Informação**: Entropia de Shannon aplicada ao espectro

## Limitações e Avisos

⚠️ **Este é um sistema de análise de sinais, NÃO um dispositivo médico**
- Os resultados devem ser interpretados por profissional qualificado
- A classificação sugerida é probabilística e não constitui diagnóstico
- A qualidade da análise depende da estabilidade do sensor e posicionamento adequado

## Tecnologias Utilizadas

- **Frontend**: HTML5, Tailwind CSS
- **Visualização**: Chart.js
- **Processamento**: JavaScript puro (FFT, Welch, Wavelets)
- **Exportação**: jsPDF para relatórios
- **PWA**: Funciona offline após primeiro carregamento

## Aplicações Típicas

- Quantificação objetiva de tremores em contexto clínico
- Monitoramento da progressão ou resposta terapêutica
- Pesquisa em distúrbios do movimento
- Educação em análise de sinais biomédicos

## Privacidade

✅ Todos os dados são processados localmente no navegador
✅ Nenhuma informação é enviada para servidores externos
✅ Arquivos importados permanecem apenas na memória do navegador
```

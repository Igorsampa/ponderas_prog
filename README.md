# Ponderada programação

## Serviços de NLP na Nuvem AWS

Este documento apresenta alguns dos principais serviços de Processamento de Linguagem Natural (NLP) oferecidos pela Amazon Web Services (AWS). Cada item inclui um exemplo de uso, com foco em aplicações práticas e, quando possível, utilização por meio de requisições HTTP (sem depender de SDKs específicos da AWS).

---

### 1. Amazon Comprehend – Análise de Sentimento

**O que faz:**  
Classifica o sentimento de um texto como positivo, negativo, neutro ou misto.

**Exemplo de uso:**  
Classificar se uma notícia sobre uma empresa tem tom positivo ou negativo.

**Exemplo de chamada HTTP:**
```http
POST https://comprehend.<região>.amazonaws.com/
X-Amz-Target: Comprehend_20171127.DetectSentiment
Content-Type: application/x-amz-json-1.1

{
  "Text": "A empresa cresceu 200% no último ano.",
  "LanguageCode": "pt"
}
```

---

### 2. Amazon Comprehend – NER

**O que faz:**  
Identifica nomes de pessows, locais, organizações, eventos, etc.

**Exemplo de uso:**  
Detectar nomes de empresas envolvidas em notícias jurídicas.

**Exemplo de chamada HTTP:**
```http
POST https://comprehend.<região>.amazonaws.com/
X-Amz-Target: Comprehend_20171127.DetectEntities
Content-Type: application/x-amz-json-1.1

{
  "Text": "A empresa Odebrecht foi investigada na operação Lava Jato.",
  "LanguageCode": "pt"
}
```

---

### 3. Amazon Comprehend – Extração de Frases-Chave

**O que faz:**  
Extrai termos ou expressões que resumem o conteúdo do texto.

**Exemplo de uso:**  
Gerar um resumo simples a partir de trechos grandes de texto.

---

### 4. Amazon Comprehend – Detecção de Idioma

**O que faz:**  
Detecta automaticamente o idioma dw texto enviado.

**Exemplo de uso:**  
Filtrar apenas conteúdos escritos em português antes de aplicar outras análises.

---

### 5. Amazon Bedrock – Geração de Texto com LLMs

**O que faz:**  
Permite usar modelos como Claude ou GPT para geração de texto (resumos, explicações, reformulações).

**Exemplo de uso:**  
Reescrever um parágrafo com linguagem mais clara ou gerar explicações automáticas.

**Obs:**  
Este serviço é mais avançado e precisa de configuração específica de autenticação AWS.

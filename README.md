🧠 Desafio — Prompt Engineering

O desafio de Prompt Engineering tem como objetivo aplicar técnicas estratégicas na formulação de prompts para extrair respostas precisas, relevantes e detalhadas de ferramentas de IA generativa.

A seguir estão as 4 questões propostas e os respectivos prompts criados com as respostas obtidas a partir do uso do ChatGPT (OpenAI).

1️⃣ Como o algoritmo de Ray Tracing calcula a cor de um pixel
🎯 Objetivo

Explicar o funcionamento do algoritmo de Ray Tracing no cálculo da cor de um pixel renderizado.

💡 Técnica aplicada

Prompt de papel e contexto + nível técnico desejado

🧠 Prompt

Você é um especialista em computação gráfica. Explique de forma técnica e detalhada como o algoritmo de Ray Tracing calcula a cor de um pixel em uma imagem renderizada, descrevendo cada etapa do processo (lançamento de raios, interseção, iluminação, reflexão e refração).

✅ Resposta

O Ray Tracing simula o comportamento físico da luz. O processo segue as etapas:

Um raio é lançado da câmera através de cada pixel da imagem.

O algoritmo identifica o primeiro objeto atingido pelo raio.

Calcula-se a cor local com base nas fontes de luz (modelo de iluminação, como Phong).

Raios secundários são lançados para simular reflexão e refração.

A cor final do pixel é o resultado da combinação ponderada dessas interações.
Esse método produz imagens com alto realismo, simulando sombras, brilhos e transparências.

2️⃣ Decomposição numérica de 142.981
🎯 Objetivo

Decompor o número 142.981 mostrando o valor posicional de cada algarismo.

💡 Técnica aplicada

Prompt direto e instrutivo com formato esperado de saída

🧠 Prompt

Decomponha o número 142.981 mostrando o valor posicional de cada algarismo (centenas de milhar, dezenas de milhar, etc.) e apresente o resultado de forma clara e matemática.

✅ Resposta

142.981 = 100.000 + 40.000 + 2.000 + 900 + 80 + 1
👉 Decomposição posicional:
(1 × 100.000) + (4 × 10.000) + (2 × 1.000) + (9 × 100) + (8 × 10) + (1 × 1)

3️⃣ Personagens de As Crônicas de Gelo e Fogo inspirados em Maquiavel
🎯 Objetivo

Identificar personagens com características baseadas na filosofia de Maquiavel.

💡 Técnica aplicada

Prompt analítico com referência cruzada (obra + filosofia)

🧠 Prompt

Analise os personagens da obra As Crônicas de Gelo e Fogo, de George R. R. Martin, e identifique quais apresentam traços inspirados na filosofia de Maquiavel, especialmente nas ideias de O Príncipe. Explique brevemente o motivo de cada associação.

✅ Resposta

Tywin Lannister: Governante pragmático, coloca o poder e a estabilidade acima da moral — típico de Maquiavel.

Petyr Baelish (Mindinho): Manipulador político que busca ascensão por meio da astúcia — “os fins justificam os meios”.

Cersei Lannister: Usa o medo e o controle como ferramentas de poder.

Varys: Age em prol da estabilidade do reino, mesmo recorrendo a mentiras.

Esses personagens incorporam a visão maquiavélica de liderança baseada na estratégia e na manutenção do poder.

4️⃣ Endpoint com FastAPI para validação e processamento de Item
🎯 Objetivo

Criar um endpoint que receba, valide e retorne um objeto Item com um identificador uuid gerado dinamicamente.

💡 Técnica aplicada

Prompt de instrução técnica com formato de saída em código

🧠 Prompt

Crie um endpoint em Python usando o framework FastAPI que receba um objeto chamado Item com os campos:

nome: string (máx. 25 caracteres)

valor: float

data: tipo date, que não pode ser superior à data atual.
O endpoint deve validar os valores e retornar o mesmo objeto com um campo adicional uuid, gerado dinamicamente.

✅ Resposta (código)
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel, Field, validator
from datetime import date
import uuid

app = FastAPI()

class Item(BaseModel):
    nome: str = Field(..., max_length=25)
    valor: float
    data: date

    @validator("data")
    def validar_data(cls, v):
        if v > date.today():
            raise ValueError("A data não pode ser superior à data atual.")
        return v

@app.post("/item")
def criar_item(item: Item):
    item_dict = item.dict()
    item_dict["uuid"] = str(uuid.uuid4())
    return item_dict

🧩 Conclusão

O desafio demonstrou como técnicas de Prompt Engineering (clareza, contexto, papel e formato esperado) influenciam diretamente a qualidade e precisão das respostas geradas por uma IA.
Cada questão aplicou um tipo de prompt diferente, adaptado ao tipo de tarefa — teórica, numérica, analítica e técnica.

💻 Autor(a)

Mariana Freitas de Azevedo

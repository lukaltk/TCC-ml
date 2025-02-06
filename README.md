# TCC-ml

Essas quatro métricas – **Acurácia, Precisão, Revocação (Recall) e F1-Score** – são fundamentais para avaliar o desempenho de um modelo de classificação. Vamos entender cada uma:  

---

### **1️⃣ Acurácia (Accuracy)**
**Mede a proporção de previsões corretas em relação ao total de previsões.**  

\[
\text{Acurácia} = \frac{\text{Nº de previsões corretas}}{\text{Total de amostras}}
\]

✅ **Vantagem:** Funciona bem quando as classes estão balanceadas.  
❌ **Problema:** Pode ser enganosa em **dados desbalanceados**. Exemplo: Se 95% dos dados pertencem à classe A, um modelo que sempre prevê A terá 95% de acurácia, mas não será útil.  

📌 **Exemplo:**  
Se temos **100 amostras** e o modelo acerta **90**, a acurácia é **90%**.  

---

### **2️⃣ Precisão (Precision)**
**Mede quantas das previsões positivas estavam corretas.**  

\[
\text{Precisão} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Positives (FP)}}
\]

✅ **Importante quando os falsos positivos são críticos.**  
📌 **Exemplo:** Em um teste para detectar **câncer**, um falso positivo pode causar pânico desnecessário.  

🔹 **Interpretação**:  
- **Alta precisão** → Poucos falsos positivos.  
- **Baixa precisão** → Muitos falsos positivos.  

---

### **3️⃣ Revocação (Recall) (Sensibilidade ou Sensibilidade Verdadeira)**
**Mede quantas das instâncias positivas foram corretamente identificadas.**  

\[
\text{Revocação} = \frac{\text{True Positives (TP)}}{\text{True Positives (TP)} + \text{False Negatives (FN)}}
\]

✅ **Importante quando os falsos negativos são críticos.**  
📌 **Exemplo:** Em um teste para **doença grave**, um falso negativo significa que um paciente doente não será tratado!  

🔹 **Interpretação**:  
- **Alta revocação** → Poucos falsos negativos (ótimo para detectar doenças).  
- **Baixa revocação** → Muitos falsos negativos.  

---

### **4️⃣ F1-Score (Média Harmônica entre Precisão e Recall)**
**Combina Precisão e Recall em uma única métrica balanceada.**  

\[
\text{F1-Score} = 2 \times \frac{\text{Precisão} \times \text{Revocação}}{\text{Precisão} + \text{Revocação}}
\]

✅ **Útil quando há desequilíbrio entre classes.**  
📌 **Exemplo:** Se um modelo tem **alta precisão mas baixa revocação**, ou vice-versa, o F1-Score ajudará a encontrar um equilíbrio.  

🔹 **Interpretação**:  
- **F1 próximo de 1** → Bom equilíbrio entre precisão e recall.  
- **F1 baixo** → O modelo tem problemas com precisão ou recall.  

---

### **Resumo das Diferenças**
| Métrica        | Pergunta que responde | Quando usar? |
|---------------|----------------------|-------------|
| **Acurácia**  | "Quantos acertos o modelo fez no total?" | Se as classes estão **balanceadas**. |
| **Precisão**  | "Dos positivos que o modelo previu, quantos estavam certos?" | Quando **falsos positivos** são mais graves. |
| **Recall**    | "Dos casos realmente positivos, quantos o modelo encontrou?" | Quando **falsos negativos** são mais graves. |
| **F1-Score**  | "Existe equilíbrio entre precisão e recall?" | Quando há **desbalanceamento entre classes**. |

---

### **Exemplo Prático**
Vamos supor um modelo de **detecção de spam**, onde:  
- **TP (True Positives)** → E-mails corretamente classificados como spam.  
- **FP (False Positives)** → E-mails bons classificados incorretamente como spam.  
- **FN (False Negatives)** → E-mails de spam não detectados.  

Se tivermos:  
✅ **Alta precisão** → Poucos e-mails bons sendo marcados como spam.  
✅ **Alta revocação** → A maioria dos spams são detectados corretamente.  
➡ **F1-Score** nos dirá se o modelo tem um bom equilíbrio entre esses dois fatores.  

Se precisar de código em **Python** para calcular essas métricas, me avise! 🚀
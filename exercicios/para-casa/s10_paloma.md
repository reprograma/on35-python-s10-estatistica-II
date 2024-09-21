Objetivo:

Verificar se a altura média da turma é significativamente diferente de 161 cm.
Dados da Amostra:

Altura da turma (em cm): [165,157,163,170,167,161,160,170,157,160,157,168,162,170,167,165,166,158,174,169,163,174,162,170,155,154,158,160,166]
Perguntas:

Calcule a estatística z e o valor p para verificar se a altura média da turma é significativamente diferente de 161 cm.

Interprete os resultados: Preciso saber se rejeitou ou não a hipótese nula.


```python
import numpy as np
from statsmodels.stats.weightstats import ztest

#Amostra
altura_turma = np.array([165,157,163,170,167,161,160,170,157,160,157,168,162,170,167,165,166,158,174,169,163,174,162,170,155,154,158,160,166])
media_nacional = 161
media_turma = int(np.mean(altura_turma))


# Teste z para uma amostra

z_statistic, p_value = ztest(altura_turma, value=media_nacional)

print(f"Média da altura da  turma: {media_turma}cm")
print(f"Média da altura da população feminina nacional: {media_nacional}cm")
print(f"z-statistic: {z_statistic:.4f}")
print(f"p-value:{p_value:.4f} ")


#Nível de significância
nivel = 0.05

if p_value < nivel:  
    print("A média da altura das alunas não é igual a média da população feminina nacional")  # rejeita H0 porque não é igual a hipotese
else:
    print("A média da altura das alunas é igual a média da população feminina nacional")

```

Resultado:

A altura média da turma é maior que a média nacional

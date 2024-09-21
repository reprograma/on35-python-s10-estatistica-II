```python
import numpy as np
from statsmodels.stats.weightstats import ztest


#Nível de significância
ns = 0.05

#Amostra
altura_turma = np.array([165,157,163,170,167,161,160,170,157,160,157,168,162,170,167,165,166,158,174,169,163,174,162,170,155,154,158,160,166])
media_nacional = 161
media_alunas = int(np.mean(altura_turma))


# Teste z para uma amostra
z_statistic, p_value = ztest(altura_turma, value=media_nacional)

print(f"Média da altura das alunas: {media_alunas}cm")
print(f"Média da altura da população feminina nacional: {media_nacional}cm")
print(f"z-statistic: {z_statistic:.4f}")
print(f"p-value:{p_value:.4f} ")
```

if p_value < ns:
    print("Rejeitamos a hipótese nula, não há evidências de que a média da altura das alunas seja igual a média da população feminina nacional")
else:
    print("Não rejeitamos a hipótese nula, há evidências de que a média da altura das alunas é igual a média da população feminina nacional")

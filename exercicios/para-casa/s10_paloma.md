
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## **Formulando as hipósteses:**\n",
    "\n",
    "A hipótese nula(H₀): A altura média das alunas da turma on35 é igual a média da população feminina nacional, que é 161cm.\n",
    "\n",
    "A hipótese alternativa (H₁): A média da altura das alunas da turma on35 não é igual a média da população feminina nacional, que é 161cm.\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Média da altura das alunas: 163cm\n",
      "Média da altura da população feminina nacional: 161cm\n",
      "Teste z para uma amostra:\n",
      "z-statistic: 2.6201\n",
      "p-value:0.0088 \n",
      "Rejeitamos a hipótese nula, não há evidências de que a média da altura das alunas seja igual a média da população feminina nacional\n"
     ]
    }
   ],
   "source": [
    "import numpy as np\n",
    "from statsmodels.stats.weightstats import ztest\n",
    "\n",
    "#Nível de significância\n",
    "ns = 0.05\n",
    "\n",
    "\n",
    "# Dados da amostra\n",
    "altura_turma = np.array([165,157,163,170,167,161,160,170,157,160,157,168,162,170,167,165,166,158,174,169,163,174,162,170,155,154,158,160,166])\n",
    "media_nacional = 161\n",
    "media_alunas = int(np.mean(altura_turma))\n",
    "# Teste z para uma amostra\n",
    "z_statistic, p_value = ztest(altura_turma, value=media_nacional)\n",
    "\n",
    "print(f\"Média da altura das alunas: {media_alunas}cm\")\n",
    "print(f\"Média da altura da população feminina nacional: {media_nacional}cm\")\n",
    "print(f\"z-statistic: {z_statistic:.4f}\")\n",
    "print(f\"p-value:{p_value:.4f} \")\n",
    "\n",
    "\n",
    "if p_value < ns:\n",
    "    print(\"Rejeitamos a hipótese nula, não há evidências de que a média da altura das alunas seja igual a média da população feminina nacional\")\n",
    "else:\n",
    "    print(\"Não rejeitamos a hipótese nula, há evidências de que a média da altura das alunas é igual a média da população feminina nacional\")\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "***Conclusão:***\n",
    "\n",
    "Nível de significância usado no testes estatísticos foi 0.05 (ou 5%), e o p-value é de (0.0088) que é menor que 0.05 portanto, rejeitamos a hipótese nula.\n",
    "\n",
    "***Interpretação Final:***\n",
    "\n",
    "A altura média da amostra de alturas da turma é significativamente diferente de 161 cm. Em outras palavras, há evidências estatisticamente significativas para afirmar que a altura média da turma difere da altura média da população feminina nacional que é 161 cm."
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.12.0"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}

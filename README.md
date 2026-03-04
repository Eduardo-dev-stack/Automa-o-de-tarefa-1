[Automação(teste 1).py](https://github.com/user-attachments/files/25741219/Automacao.teste.1.py)
import pyautogui
import pandas as pd
import time
pyautogui.press("win")
pyautogui.write("Chrome")
pyautogui.press("enter")
pyautogui.PAUSE = 2

Link = "https://dlp.hashtagtreinamentos.com/python/intensivao/login"
time.sleep(5)

pyautogui.write(Link)
pyautogui.press("enter")

pyautogui.click(x=618, y=379)

pyautogui.write("dududeliragalinndo@gmail.com") #email
pyautogui.press("tab")
pyautogui.write("123456789") #senha 
pyautogui.click(x=695, y=537)
time.sleep(5)



tabela = pd.read_csv(r"C:\Users\dudud\Downloads\produtos.csv")

print(tabela)

for linha in tabela.index:
    pyautogui.click(x=455, y=258)
    codigo = tabela.loc[linha, "codigo"]
    pyautogui.write(str(codigo))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "marca"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "tipo"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "categoria"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "preco_unitario"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "custo"]))
    pyautogui.press("tab")
    obs = tabela.loc[linha, "obs"]
    if not pd.isna(obs):
        pyautogui.write(str(tabela.loc[linha, "obs"]))
    pyautogui.press("tab")
    pyautogui.press("enter")  

    pyautogui.scroll(5000)

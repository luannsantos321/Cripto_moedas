# Cripto_moedas
# Webscraping analise  de preço  de criptomoedas
Utilizando a biblioteca BeautifulSoup e requests para pegar o link da página e pegar o elementos necessário, consegui ter dados de valores das criptomoedas escolhidas por mim.

# Buscando as linhas que contém os valores das cripto
      sleep(3)
      link = "https://coinmarketcap.com/"
      requisicao = requests.get(link)
      soup = BeautifulSoup(requisicao.text, 'html.parser')
      tbody = soup.find('table')
      linhas = tbody.find_all('tr')
      

    
# Pegando cada linha e colocando num tipo de mecanismo de dados de python, a lista.
      for linha in linhas:
            valores = linha.find_all('td')
            for valor in valores:
            if valor.text != '':
            texto.append(valor.text)

# Separado em variaveis para poder ser mostrado no terminal
      BitcoinBTC = texto[1:3]
      EthereumETH = texto[10:12]
      Tether = texto[19:21]
      BNBBNB = texto[28:30]
      print(BitcoinBTC,EthereumETH,Tether,BNBBNB)

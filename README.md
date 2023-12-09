# with_par_fechar_BD

import sqlite3
from contextlib import closing
with sqlite3.connect("agenda.db") as conexao:
  with closing(conexao.cursor()) as cursor:
    cursor.execute("select * from agenda")
    while True:
      resultado = cursor.fetchone()
      if resultado is None:
        break
      print(f"Nome: {registro[0]}\nTelefone: {registro[1]}")

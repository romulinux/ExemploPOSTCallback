# Exemplo de Integração POST (Callback) com a Monetizze
Esse é um script em PHP de exemplo de como o POST (callback) da Monetizze pode ser tratado


Para integrar a Monetizze com seu sistema.

- Vá no menu ferramentas
- Clique na opção postback
- Selecione Tipo (Server to Server)
- No campo URL coloque a url do seus sistema que receberá o post callback da Monetizze


*Botão de teste envia um produto exemplo chamado X-Wing


# JSON retornado

```json
{
  "venda": {
    "codigo": "999999999", // numérico
    "plano": "999999999", // numérico
    "dataInicio": "2021-10-10 23:59:59", // "Y-m-d H:i:s",
    "dataFinalizada": "2021-10-10 23:59:59", // "Y-m-d H:i:s",
    "meioPagamento": "Monetizze", // "Monetizze" | ""
    "formaPagamento": "Boleto", // "Boleto" | "Cartão de crédito" | "Pix" | "Grátis" | "Débito online"
    "garantiaRestante": 0, // numérico
    "status": "Cancelada", // "Abandono de Checkout" | "Aguardando pagamento" | "Finalizada" | "Cancelada" | "Devolvida" | "Completa"
    "valor": "69.90", // número real
    "quantidade": "1", // numérico
    "valorRecebido": "16.58", // decimal
    "onebuyclick": "0", // "0" | "1"
    "venda_upsell": null, // numérico | null
    "tipo_frete": null, // null | "0" | "10" | "11" | "3" | "3220" | "3298" | "4" | "4014" | "4510 | "999997" | "999998" | "999999"
    "descr_tipo_frete": null, // null | " " | "" | "0" | "Correios Frete Super expresso" | "Correios Frete-gratis" | "Correios PAC Contrato TA" | "Correios PAC" | "Correios SEDEX" | "Freteasy PAC" | "Padrão" | "Total Express | "Valor Fixo (Grátis)" | "Valor Fixo"
    "frete": "0.00", // decimal
    "cupom": null, // null | "string" (código do cupom)
    "src": "", // "" | string
    "utm_source": "", // "" | string
    "utm_medium": "", // "" | string
    "utm_content": "", // "" | string
    "utm_campaign": "", // "" | string
    "linkBoleto": "https:\/\/dominio.com.br", // string
    "linha_digitavel": "99999.99999 99999.999999 99999.99999 9 99999999999999", // string
    "parcelas": 1 // numérico
  },
  "chave_unica": "ffffffffffffffffffffffffffffffff", // string (disponível em https://app.monetizze.com.br/ferramentas/postback)
  "plano": {
    "codigo": "999999", // numérico
    "referencia": "ZZ999999", // string
    "nome": "Nome do plano", // string
    "quantidade": "1" // numérico
  },
  "produto": {
    "codigo": "999999", // numérico
    "chave": "eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee", // string
    "nome": "Nome do produto", // string
    "categoria": "Jurídico" // "Administração e Negócios" | "Animais de Estimação" | "Arquitetura e Engenharia" | "Artes e Música" | "Auto-ajuda e Desenvolvimento Pessoal" | "Automóveis" | "Blogs e Redes Sociais" | "Casa e Jardinagem" | "Culinária, Gastronomia, Receitas" | "Design e Templates PSD, PPT ou HTML" | "Edição de Áudio, Vídeo ou Imagens" | "Educacional, Cursos Técnicos e Profissionalizantes" | "Entretenimento, Lazer e Diversão" | "Esportes e Fitness" | "Filmes e Cinema" | "Geral" | "Histórias em Quadrinhos" | "Idiomas" | "Informática" | "Internet Marketing" | "Investimentos e Finanças" | "Jogos de Cartas, Poker, Loterias" | "Jogos de Computador, Jogos Online" | "Jurídico" | "Literatura e Poesia" | "Marketing de Rede" | "Marketing e Comunicação" | "Meio Ambiente" | "Música, Bandas e Shows" | "Paquera, Sedução e Relacionamentos" | "Plugins, Widgets e Extensões" | "Produtividade e Organização Pessoal" | "Relatórios, Artigos e Pesquisas" | "Religião e Crenças" | "Romances, Dramas, Estórias e Contos" | "RPG e Jogos de Mesa" | "Saúde, Bem-estar e Beleza" | "Scripts" | "Segurança do Trabalho" | "Sexologia e Sexualidade" | "Snippets (Trechos de Vídeo)" | "Turismo" | "Pessoas com deficiência" | "Moda e vestuário" | "Produtos infantis" | "Eletrônicos" | "Eletroportáteis" | "Eletrodomésticos" | "Moveis e decoração" | "Perfumaria" | "Rascunho" | "Trader"
  },
  "comprador": {
    "nome": "Andrea Mendes velozo", // string
    "email": "andreamendesvelozo@gmail.com", // string
    "data_nascimento": null, // null | "Y-m-d H:i:s"
    "cnpj_cpf": "99870495591", // null | string
    "telefone": "99870495591", // null | string
    "cep": null, // null | string
    "endereco": null, // null | string
    "numero": null, // null | string
    "complemento": null, // null | string
    "bairro": null, // null | string
    "cidade": null, // null | string
    "estado": null, // null | string
    "pais": "BR" // "BR" | string
  },
  "tipoEvento": {
    "codigo": 3, // 1 | 2 | 3 | 4 | 6 | 7 | 101 | 102 | 103 | 104 | 105 | 106 | 120
    "descricao": "Cancelada" // "Aguardando pagamento" | "Finalizada / Aprovada" | "Cancelada" | "Devolvida (Reembolso)" | "Bloqueada" | "Completa" | "Abandono de Checkout" | "Assinatura - Ativa" | "Assinatura - Inadimplente" | "Assinatura - Cancelada" | "Assinatura - Aguardando pagamento" | "Recuperação Parcelada - Ativa" | "Recuperação Parcelada - Cancelada" | "Status do pedido - Rastreio"
  },
  "url_recuperacao": "https:\/\/dominio.com.br", // string
  "json": "{...}", // string json de todos os outros atributos
  "postback_evento": "3", // "1" | "2" | "3" | "4" | "6" | "7" | "101" | "102" | "103" | "104" | "105" | "106" | "120"
  "tipoPostback": {
    "codigo": 2, // 2 | 3 | 4 | 5 | 6 | 7
    "descricao": "Produtor" // "Produtor" | "Gerente de Afiliado" | "Afiliado" | "Co-Produtor" | "Afiliado Premium" | "Co-Afiliado"
  },
  "produtor": {
    "cnpj_cpf": "99999999999999", // string numérica {11,14}
    "nome": "Nome do produtor", // string
    "email": "email@exemplo.com" // string
  },
  "order_bump": 0, // 0 | 1
  "ecommerce": false, // false | true
  "comissoes": [
    {
      "refAfiliado": "ZZ99999999", // string
      "nome": "Nome afiliado", // string
      "email": "email@exemplo.com", // string
      "tipo_comissao": "último Clique", // "Cashback" | "Clique intermediário | "Co-Afiliado" | "Co-Produtor" | "Gerente" | "Lead" | "Primeiro Clique" | "Produtor" | "Sistema" | "Televendas" | "último Clique"
      "valor": "45.00", // decimal
      "porcentagem": "70.22000" // decimal
    }
  ],
  "pix_url": "https:\/\/dominio.com.br", // string
  "pix_imagem_qrcode": "https:\/\/dominio.com.br", // string
  "pix_codigo_qrcode": "", // string
  "callcenter": {
    "id": "qqqqqqqqqqqqqqqq", // string
    "url": "https:\/\/callcenter.monetizze.com.br\/sell\/zzzzzzzzz\/" // string
  },
  "venda_item_order_bump": [ // se "order_bump == 1"
    {
      "produto": "999999", // numérico
      "codPlano": "999999", // numérico
      "chave": "ffffffffffffffffffffffffffffffff", // string
      "nome": "Nome do produto", // string
      "descricao": "Descrição do produto", // string
      "plano": "ZZ999999", // string
      "planoNome": "Nome do plano", // string
      "cupom": null, // null | string
      "cupom_descricao": null, // null | string
      "valor": "199.00", // decimal
      "principal": "1", // "0" | "1"
      "quantidade": "5", // numérico
      "formato": "11", // "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9" | "10" | "11" | "12" | "13" | "14" | "15" | "16"
      "categoria": "37", // | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9" | "10" | "11" | "12" | "13" | "14" | "15" | "16" | "17" | "18" | "19" | "20" | "21" | "22" | "23" | "24" | "25" | "26" | "27" | "28" | "29" | "30" | "31" | "32" | "33" | "34" | "35" | "36" | "37" | "38" | "39" | "40" | "41" | "42" | "43" | "44" | "45" | "46" | "47" | "48" | "49" | "50" | "51" | "52"
      "membertizze": null // null | "0" | "2"
    }
  ],
  "codigo_venda": "99999999", // numérico
  "codigo_status": "3", // "1" | "2" | "3" | "4 | "6"
  "rastreio": {
    "status": 2, // 2 | 4 | 6 | 7 | 8
    "descricao": "Postado", // "Aguardando retirada" | "Devolvido" | "Em trânsito" | "Entregue" | "Postado"
    "codigo": "ZZ999999999BR" // string
  },
  "assinatura": {
    "codigo": "999999", // numérico
    "status": "Cancelada", // "Aguardando pagamento" | "Ativa" | "Cancelada" | "Inadimplente"
    "data_assinatura": "2021-10-10 23:59:59", // Y-m-d H:i:s
    "parcela": "1" // numérico
  },
  "ecommerce_dados": {
    "checkout": "ZZZ999999", // string
    "tempo_expiracao": 10, // numérico
    "valor_frete": 0, // numérico
    "valor_soma_produtos": 291, // numérico
    "valor_desconto": 104, // decimal
    "valor_total": 187, // decimal
    "valor_acrescimo": 0, // decimal
    "bloquear_dados_comprador": false, // false | true
    "dados_comprador": {
      "nome": "Nome comprador", // string
      "cnpj_cpf": "99999999999", // string
      "celular": null, // null | string
      "data_nascimento": null, // null | Y-m-d H:i:s
      "exigir_cnpj_cpf": false, // false | true
      "email": "comprador@email.com", // string
      "exigir_endereco_entrega": false, // false | true
      "endereco_entrega": {
        "cep": "31999999", // string
        "endereco": "Rua 99", // string
        "numero": 5, // string
        "complemento": "Qd T Lt 99", // string
        "bairro": "Santa Branca", // string
        "cidade": "Belo Horizonte", // string
        "estado": "MG", // string
        "pais": "BR" // string
      }
    },
    "produtos": [
      {
        "codigo": null, // FIX
        "nome": "Nome do produto", // string
        "preco": 97, // decimal
        "quantidade": 1, // numérico
        "descricao": "Descrição do produto", // string
        "categoria": null // FIX
      }
    ],
    "identificador": 598, // numérico
    "venda": "99999999" // numérico
  },
  "recuperacao_parcelada": {
    "codigo": "999999", // numérico
    "status": "Ativa", // "Ativa" | "Aguardando pagamento" | "Cancelada"
    "data_recuperacao_parcelada": "2021-10-10 23:59:59", // Y-m-d H:i:s
    "parcela": "5" // numérico
  }
}
```

# ceramina-industria-ltda
CREATE TABLE Clientes(
	cod_cliente INT PRIMARY KEY,
	nome_Cliente VARCHAR (20) NOT NULL,
	sobrenome_cliente VARCHAR(40) NOT NULL,
	endereco_cliente VARCHAR (40) NOT NULL,
	contatos_cliente NUMERIC (9,12) NOT NULL,
);
CREATE TABLE produtos(
	cod_produto INT PRIMARY KEY,
	nome_produto VARCHAR (30) NOT NULL,
	descricao_produto TEXT NULL,
	preco NUMERIC CHECK (preco > 0) NOT NULL,
	qnt_estoque SMALLINT DEFAULT 0	
);
CREATE TABLE pedidos(
	cod_pedido SERIAL PRIMARY KEY,
	cod_clientes INT  NOT NULL REFERENCES clientes(cod_cliente),
	cod_produto INT NOT NULL,
	qnt SMALLINT NOT NULL,
	FOREIGN KEY (cod_produto) REFERENCES produtos (cod_produto)
);

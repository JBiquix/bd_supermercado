show databases;
create database db_supermercado;
 
CREATE TABLE cliente (
    id_cliente VARCHAR(10) PRIMARY KEY,
    nome_cliente VARCHAR(100),
    cpf VARCHAR(14),
    email VARCHAR(100)
);

CREATE TABLE usuario (
    id_usuario VARCHAR(10) PRIMARY KEY,
    nome_usuario VARCHAR(100),
    cargo VARCHAR(50),
    login VARCHAR(50),
    senha VARCHAR(50),
    nivel_permissao VARCHAR(20)
);

CREATE TABLE fornecedor (
    id_fornecedor VARCHAR(10) PRIMARY KEY,
    nome_fornecedor VARCHAR(100),
    cnpj VARCHAR(18),
    contato VARCHAR(100)
);

CREATE TABLE produto (
    id_produto VARCHAR(10) PRIMARY KEY,
    nome_produto VARCHAR(100),
    categoria VARCHAR(50),
    preco_custo DECIMAL(10,2),
    preco_venda DECIMAL(10,2),
    codigo_barras VARCHAR(20),
    quantidade_estoque INT,
    validade DATE,
    id_fornecedor VARCHAR(10),
    FOREIGN KEY (id_fornecedor) REFERENCES fornecedor(id_fornecedor)
);

CREATE TABLE venda (
    id_venda VARCHAR(10) PRIMARY KEY,
    data_hora DATETIME,
    valor_total DECIMAL(10,2),
    id_cliente VARCHAR(10),
    id_usuario VARCHAR(10),
    dinheiro DECIMAL(10,2),
    cartao_debito DECIMAL(10,2),
    cartao_credito DECIMAL(10,2),
    pix DECIMAL(10,2),
    vale_alimentacao DECIMAL(10,2),
    FOREIGN KEY (id_cliente) REFERENCES cliente(id_cliente),
    FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario)
);

CREATE TABLE item_venda (
    id_item_venda VARCHAR(10) PRIMARY KEY,
    id_venda VARCHAR(10),
    id_produto VARCHAR(10),
    quantidade INT,
    preco_venda_unidade DECIMAL(10,2),
    desconto_aplicado DECIMAL(10,2),
    FOREIGN KEY (id_venda) REFERENCES venda(id_venda),
    FOREIGN KEY (id_produto) REFERENCES produto(id_produto)
);

CREATE TABLE telefone (
    telefone_PK INT AUTO_INCREMENT PRIMARY KEY,
    telefone VARCHAR(15),
    id_cliente_FK VARCHAR(10),
    FOREIGN KEY (id_cliente_FK) REFERENCES cliente(id_cliente)
);

CREATE TABLE realiza (
    id_venda VARCHAR(10),
    id_usuario VARCHAR(10),
    FOREIGN KEY (id_venda) REFERENCES venda(id_venda),
    FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario)
);

CREATE TABLE associado (
    id_venda VARCHAR(10),
    id_cliente VARCHAR(10),
    FOREIGN KEY (id_venda) REFERENCES venda(id_venda),
    FOREIGN KEY (id_cliente) REFERENCES cliente(id_cliente)
);

CREATE TABLE pode (
    id_item_venda VARCHAR(10),
    id_venda VARCHAR(10),
    FOREIGN KEY (id_item_venda) REFERENCES item_venda(id_item_venda),
    FOREIGN KEY (id_venda) REFERENCES venda(id_venda)
);

CREATE TABLE aparecer (
    id_venda VARCHAR(10),
    id_produto VARCHAR(10),
    FOREIGN KEY (id_venda) REFERENCES venda(id_venda),
    FOREIGN KEY (id_produto) REFERENCES produto(id_produto)
);

CREATE TABLE pertence (
    id_fornecedor VARCHAR(10),
    id_produto VARCHAR(10),
    FOREIGN KEY (id_fornecedor) REFERENCES fornecedor(id_fornecedor),
    FOREIGN KEY (id_produto) REFERENCES produto(id_produto)
);

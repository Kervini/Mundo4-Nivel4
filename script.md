create database logimove;
GO
use logimove;
GO
CREATE TABLE Drivers (
    DriverID INT IDENTITY(1,1),
    Nome VARCHAR(100) NOT NULL,
    Cnh VARCHAR(20) NOT NULL,
    Endereco VARCHAR(200),
    Contato VARCHAR(50),
	CONSTRAINT pk_drivers PRIMARY KEY (DriverID)
);
GO
CREATE TABLE Clients (
    ClientID INT IDENTITY(1,1),
    Nome VARCHAR(100) NOT NULL,
    Empresa VARCHAR(100) NOT NULL,
    Endereco VARCHAR(200),
    Contato VARCHAR(50),
	CONSTRAINT pk_clients PRIMARY KEY (ClientID)
);
GO
CREATE TABLE Orders (
    OrderID INT IDENTITY(1,1),
    ClientID INT NOT NULL,
    DriverID INT NOT NULL,
    DetalhesPedido TEXT,
    DataEntrega DATE,
    Status VARCHAR(50),
	CONSTRAINT pk_orders PRIMARY KEY (OrderID),
    CONSTRAINT fk_orders_clients FOREIGN KEY (ClientID) REFERENCES Clients(ClientID),
    CONSTRAINT fk_orders_drivers FOREIGN KEY (DriverID) REFERENCES Drivers(DriverID)
);
GO
INSERT INTO Drivers(Nome, Cnh, Endereco, Contato) values 
('Marcos Antonio', '44438993254', 'Rua Carlos Drumond de Andrade, São José dos Campos', '99974396106'),
('José Silva Souza', '21435648506', 'Rua Antônio de Oliveira Valente Neto, Campinas', '46979676078'),
('Lucas Miranda', '09546943834', 'Rua Leste C, Guarulhos', '22987575677'),
('Reginaldo Torres', '37473534071', 'Viela Ádamo, Guarulhos', '95996027795'),
('Carlos da Silva', '35344401621', 'Rua São Judas, Cruzeiro', '69989496852'),
('Danilo Bueno Ferreira', '60677299398', 'Rua Cavalheiro Ângelo Sestini, Franco da Rocha', '61972245862'),
('Paulo Henrique Rodrigues', '54235211811', 'Rua Pinheiral, Itapecerica da Serra', '81994264362'),
('João Paulo Costa', '26104293467', 'Rua Seresta do Amor, São Paulo', '91967338549'),
('Maria Aparecida Ribeiro', '06515618804', 'Rua Expedicionário Benedicto de Souza Ferraz, Mogi das Cruzes', '68985489333'),
('Valentina Marques', '44309024710', 'Rua Áustria, Guarulhos', '63985442155'),
('Marco Tulio Domingues', '75363509926', 'Rua Mário Sardelli, São Paulo', '91973782552'),
('Leornado Henrique Souza Neto', '82613903615', 'Rua João Guanciale, Campo Limpo Paulista', '28996132379'),
('Danilo Nunes Junior', '85089805057', 'Rua Carlos Frederico, Botucatu', '48997982555'),
('Mario José da Silva Grande', '88994967114', 'Rua Seis, Jundiaí', '87981110414'),
('Henrique Gonçalves', '75746016341', 'Rua Xavier Mayer, Campinas', '67971447193');
GO
INSERT INTO Clients(Nome, Empresa, Endereco, Contato) values
('Ana Silva', 'Tech Solutions','Rua das Flores, 123', '11987654321'),
('Bruno Oliveira', 'Global Industries','Av. Central, 456', '21976543210'),
('Carla Santos', 'Innovate Ltda','Rua da Paz, 789', '31965432109'),
('Daniel Pereira', 'Future Tech','Av. das Nações, 321', '41954321098'),
('Érica Costa', 'Creative Minds','Rua Verde, 654', '51943210987'),
('Felipe Almeida', 'Eco Solutions','Av. do Sol, 987', '61932109876'),
('Gabriela Lima', 'Smart Systems','Rua do Comércio, 234', '71921098765'),
('Hugo Martins', 'Alpha Corp','Av. da Liberdade, 432', '81910987654'),
('Isabella Rocha','NextGen Technologies','Rua Nova, 567', '91909876543'),
('João Mendes','Bright Ideas','Av. da Esperança, 876', '11898765432'),
('Karen Souza','Visionary Concepts', 'Rua do Futuro, 135', '21887654321'),
('Lucas Ferreira','Synergy Group','Av. das Artes, 246', '31876543210'),
('Mariana Oliveira','Prime Innovations','Rua do Progresso, 357', '41865432109'),
('Natan Dias','Optimal Solutions','Av. dos Sonhos, 468', '51854321098'),
('Otávio Santos','Dynamic Ventures','Rua da Criatividade, 579', '61843210987'),
('Paula Costa','Pioneer Enterprises','Av. da Tecnologia, 680', '71832109876'),
('Quirino Almeida','Horizon LLC','Rua das Ideias, 791', '81821098765'),
('Raquel Nascimento','Inspire Inc.', 'Av. do Crescimento, 802', '91810987654'),
('Samuel Lima','Summit Enterprises','Rua da Inovação, 913', '11809876543'),
('Tânia Rocha','Nexus Corp', 'Av. da Sabedoria, 104', '21798765432'),
('Uriel Costa','Genesis Group', 'Rua da Transformação, 215', '31787654321'),
('Vanessa Martins','Catalyst Co.', 'Av. do Avanço, 326', '41776543210'),
('Wagner Almeida','Quantum Solutions', 'Rua do Despertar, 437', '51765432109'),
('Yara Pereira','Unity Partners', 'Av. do Entendimento, 548','61754321098'),
('Zé Oliveira','Impact Innovations', 'Rua do Sucesso, 659', '71743210987'),
('Ana Paula','Engage Ltda', 'Av. do Potencial, 760', '81732109876'),
('Bruno Costa','Inspire Group', 'Rua da Visão, 871', '91721098765'),
('Carla Lima','Revolution Corp', 'Av. da Mudança, 982', '11710987654'),
('Daniel Nascimento','Progress LLC', 'Rua da Evolução, 103', '21709876543'),
('Érica Almeida','Vanguard Solutions', 'Av. da Excelência, 214', '31698765432'),
('Felipe Santos','Aspire Inc.', 'Rua do Desenvolvimento, 325', '41687654321'),
('Gabriela Rocha','Ascend Group', 'Av. da Performance, 436', '51676543210'),
('Hugo Ferreira','Envision Ltda', 'Rua do Brilho, 547', '61665432109'),
('Isabella Mendes','Thrive Technologies', 'Av. do Progresso, 658', '71654321098'),
('João Costa','Flourish Inc.', 'Rua da Criatividade, 769', '81643210987'),
('Karen Oliveira', 'Leap Forward', 'Av. do Conhecimento, 870', '91632109876'),
('Lucas Santos', 'Breakthrough Group', 'Rua da Ambição, 981', '11621098765'),
('Mariana Lima', 'Progress Partners', 'Av. da Ação, 109', '21610987654'),
('Natan Almeida', 'Growth Strategies', 'Rua da Esperança, 210', '31609876543'),
('Otávio Rocha', 'Success Inc.', 'Av. do Resultado, 321', '41598765432'),
('Paula Santos', 'Thrive Ventures', 'Rua da Estratégia, 432', '51587654321'),
('Quirino Nascimento', 'Visionary Group', 'Av. do Impacto, 543','61576543210'),
('Raquel Lima', 'Inspire Partners', 'Rua do Destino, 654', '71565432109'),
('Samuel Almeida', 'Ultimate Solutions', 'Av. da Inspiração, 765', '81554321098'),
('Tânia Costa', 'Creative Ventures', 'Rua do Progresso, 876','91543210987'),
('Uriel Santos', 'Nova Corp', 'Av. do Desenvolvimento, 987', '11532109876'),
('Vanessa Rocha', 'Catalyst Solutions', 'Rua da Inovação, 1098','21521098765'),
('Wagner Pereira', 'Synergy Innovations', 'Av. do Amanhã, 2109','31510987654'),
('Yara Almeida', 'Apex Partners', 'Rua do Crescimento, 3210', '41509876543'),
('Zé Costa', 'Impact Group', 'Av. do Sucesso, 4321', '51498765432');
GO
INSERT INTO Orders (ClientID, DriverID, DetalhesPedido, DataEntrega, Status) values
(23, 1, 'Pedido de entrega de 50 caixas de eletrônicos para a loja TechShop, Rua das Inovações, 123', '2023-05-15', 'CONCLUIDO'),
(12, 14, 'Envio de 200kg de produtos alimentícios para o supermercado FreshMarket, Av. das Palmeiras, 456', '2023-06-02', 'CONCLUIDO'),
(47, 6, 'Transporte de 30 móveis da fábrica Móveis Luxo para a residência de Ana Silva, Rua do Sol, 789', '2023-06-20', 'CONCLUIDO'),
(6, 10, 'Entrega de 100 pacotes de roupas para a Boutique Estilo, Av. dos Modistas, 321', '2023-07-10', 'CONCLUIDO'),
(34, 12, 'Envio de equipamentos de informática para a empresa Tech Solutions, Rua da Tecnologia, 654', '2023-07-25', 'CONCLUIDO'),
(19, 5, 'Transporte de 75 toneladas de material de construção para a obra na Av. do Progresso, 987', '2023-08-05', 'CANCELADO'),
(50, 9, 'Entrega de 5 pallets de bebidas para o Bar do Zé, Rua da Alegria, 135', '2023-08-18', 'CONCLUIDO'),
(29, 2, 'Envio de 40 caixas de cosméticos para a loja Beleza & Cia, Av. da Estética, 246', '2023-09-01', 'CONCLUIDO'),
(3, 8, 'Transporte de 20 eletrodomésticos para a loja EletroMania, Rua das Compras, 357', '2023-09-14', 'CONCLUIDO'),
(41, 4, 'Entrega de 150kg de frutas e verduras para o Mercado Verde, Av. da Saúde, 468', '2023-09-29', 'CONCLUIDO'),
(25, 11, 'Envio de 10 toners de impressora para a empresa Escritório Criativo, Rua do Trabalho, 579', '2023-10-04', 'CONCLUIDO'),
(7, 3, 'Transporte de 60 caixas de brinquedos para a loja Brincadeira Garantida, Av. da Diversão, 680', '2023-10-17', 'CONCLUIDO'),
(14, 7, 'Entrega de 8 pallets de livros para a livraria Conhecimento, Rua da Literatura, 791', '2023-10-28', 'CONCLUIDO'),
(38, 1, 'Envio de 50 garrafas de vinho para o Restaurante Gourmet, Av. dos Sabores, 802', '2023-11-11', 'CONCLUIDO'),
(4, 14, 'Transporte de 15 peças de arte para a Galeria de Artes, Rua da Cultura, 913', '2023-11-15', 'CONCLUIDO'),
(48, 6, 'Entrega de 100kg de material escolar para a escola Ensino Criativo, Av. da Educação, 104', '2023-12-01', 'CONCLUIDO'),
(32, 10, 'Envio de 25 máquinas de café para o escritório Coffee Lovers, Rua da Manhã, 215', '2023-12-20', 'CONCLUIDO'),
(10, 12, 'Transporte de 150 caixas de produtos de limpeza para a distribuidora Limpeza Eficaz, Av. da Higiene, 326', '2024-01-05', 'CONCLUIDO'),
(22, 5, 'Entrega de 20 pallets de móveis de escritório para a empresa Trabalhar Melhor, Rua do Trabalho, 437', '2024-01-14', 'CANCELADO'),
(15, 9, 'Envio de 50 eletrônicos para a loja Gadget Store, Av. do Futuro, 548', '2024-01-29', 'CANCELADO'),
(35, 2, 'Transporte de 300kg de grãos para a indústria AlimentaMais, Rua do Alimento, 659', '2024-02-02', 'CONCLUIDO'),
(18, 8, 'Entrega de 40 caixas de ferramentas para a loja Ferramentas & Cia, Av. da Construção, 760', '2024-02-18', 'CONCLUIDO'),
(9, 4, 'Envio de 100 garrafas de óleo para o Mercado do Bairro, Rua da Cozinha, 871', '2024-03-10', 'CONCLUIDO'),
(27, 11,'Transporte de 10 pallets de papel para a gráfica Papel e Arte, Av. do Papel, 982', '2024-03-22', 'CONCLUIDO'),
(2, 3, 'Entrega de 5 toners de impressora para a empresa Documentos Rápidos, Rua do Escritório, 103', '2024-04-01', 'CONCLUIDO'),
(43, 7, 'Envio de 30 caixas de remédios para a farmácia Saúde em Dia, Av. da Medicina, 214', '2024-04-15', 'CONCLUIDO'),
(1, 1, 'Transporte de 12 pallets de eletrônicos para o depósito da loja Eletrônica Total, Rua da Tecnologia, 325', '2024-04-30', 'CONCLUIDO'),
(36, 14, 'Entrega de 70kg de café para o Café da Manhã, Av. dos Aromas, 436', '2024-05-06', 'CONCLUIDO'),
(24, 6, 'Envio de 20 caixas de pet food para a loja Pet Shop, Rua dos Animais, 547', '2024-05-19', 'CONCLUIDO'),
(30, 10, 'Transporte de 150kg de carne para o açougue Ponto da Carne, Av. do Sabor, 658', '2024-06-03', 'CONCLUIDO'),
(39, 12, 'Entrega de 60 pallets de cimento para a construção civil na Av. dos Engenheiros, 769', '2024-06-21', 'CONCLUIDO'),
(5, 5, 'Envio de 200kg de sucos naturais para o Mercado Fresh, Rua da Saudade, 870', '2024-07-08', 'CONCLUIDO'),
(17, 9, 'Transporte de 5 pallets de eletrodomésticos para a loja EletroGiga, Av. da Inovação, 981', '2024-07-26', 'CONCLUIDO'),
(46, 2, 'Entrega de 40 caixas de acessórios de moda para a loja Fashionista, Rua do Estilo, 109', '2024-08-15', 'CONCLUIDO'),
(40, 8, 'Envio de 10 tonéis de tinta para a empresa Pintura Fina, Av. da Cor, 210', '2024-08-30', 'CONCLUIDO'),
(8, 4, 'Transporte de 20 caixas de produtos de higiene para a farmácia Bem-Estar, Rua da Saúde, 321', '2024-09-12', 'CANCELADO'),
(44, 11,'Entrega de 150kg de grãos para a cooperativa AgroBrasil, Av. do Campo, 432', '2024-09-24', 'CONCLUIDO'),
(11, 3, 'Envio de 60 caixas de doces para a confeitaria Delícias, Rua da Doçura, 543', '2024-10-06', 'CONCLUIDO'),
(20, 7, 'Transporte de 100kg de massas para a fábrica de alimentos Massas Caseiras, Av. da Gastronomia, 654', '2024-10-19', 'CONCLUIDO'),
(26, 1, 'Entrega de 30 caixas de equipamentos de segurança para a empresa Proteção Total, Rua da Segurança, 765', '2024-10-27', 'CONCLUIDO'),
(45, 14, 'Envio de 10 pallets de papelão para a fábrica Embalagens Rápidas, Av. da Embalagem, 876', '2024-11-01', 'CONCLUIDO'),
(33, 6, 'Transporte de 200kg de materiais para artesanato para a loja Arte Criativa, Rua da Criatividade, 987', '2023-05-30', 'CONCLUIDO'),
(13, 10, 'Entrega de 15 máquinas de lavar para a loja Eletro Fácil, Av. das Compras, 123', '2023-06-10', 'CONCLUIDO'),
(28, 12, 'Envio de 50 pacotes de café para a cafeteria Sabor do Dia, Rua do Café, 234', '2023-07-04', 'CONCLUIDO'),
(42, 5, 'Transporte de 30 caixas de produtos químicos para a indústria Química Verde, Av. da Indústria, 345', '2023-07-22', 'CONCLUIDO'),
(49, 9, 'Entrega de 25 pallets de móveis de jardim para a loja Verde e Amarelo, Rua do Verde, 456', '2023-08-11', 'CONCLUIDO'),
(16, 2, 'Envio de 100kg de especiarias para o restaurante Sabores do Mundo, Av. das Culinárias, 567', '2023-09-07', 'CONCLUIDO'),
(37, 8, 'Transporte de 40 caixas de acessórios eletrônicos para a loja Tech Shop, Rua da Tecnologia, 678', '2023-09-21', 'CONCLUIDO'),
(21, 4, 'Entrega de 5 pallets de produtos de limpeza para a distribuidora Limpeza Total, Av. da Limpeza, 789', '2023-10-12', 'CONCLUIDO'),
(31, 11, 'Envio de 150kg de alimentos congelados para a loja Freezer Fresh, Rua do Frio, 890', '2023-10-25', 'CONCLUIDO'),
(25, 3, 'Transporte de 20 caixas de artigos de papelaria para a papelaria Papel e Caneta, Av. da Escrita, 901', '2023-11-03', 'CONCLUIDO'),
(3, 7, 'Entrega de 70kg de legumes para o mercado Orgânicos do Bairro, Rua da Horta, 123', '2023-11-19', 'CONCLUIDO'),
(8, 1, 'Envio de 50 produtos eletrônicos para a loja de gadgets Geek Mania, Av. da Tecnologia, 234', '2023-12-05', 'CONCLUIDO'),
(29, 14, 'Transporte de 100kg de ração para a loja Pet Love, Rua dos Pets, 345', '2024-01-10', 'CONCLUIDO'),
(12, 6, 'Entrega de 10 caixas de utensílios de cozinha para a loja Casa e Cozinha, Av. do Lar, 456', '2024-01-25', 'CONCLUIDO'),
(39, 10, 'Envio de 25 caixas de material de limpeza para a empresa Limpeza Rápida, Rua do Brilho, 567', '2024-02-08', 'CONCLUIDO'),
(17, 12, 'Transporte de 80kg de café para a cafeteria Café do Mercado, Av. do Aroma, 678', '2024-02-20', 'CANCELADO'),
(42, 5, 'Entrega de 15 pallets de papel para a gráfica Impressão Ágil, Rua da Impressão, 789', '2024-03-05', 'CONCLUIDO'),
(11, 9, 'Envio de 5 tonéis de produtos químicos para a fábrica Química Limpa, Av. da Indústria, 890', '2024-03-18', 'CONCLUIDO'),
(34, 2, 'Transporte de 200kg de produtos de beleza para a loja Estética Bella, Rua da Beleza, 901', '2024-04-03', 'CONCLUIDO'),
(49, 8, 'Entrega de 40 pacotes de carnes curadas para o açougue Fumaça e Sabor, Av. do Fumaça, 135', '2024-04-22', 'CONCLUIDO'),
(22, 4, 'Envio de 10 pallets de brinquedos para a loja Brinquedos e Companhia, Rua da Diversão, 246', '2024-05-01', 'AGUARDANDO'),
(4, 11, 'Transporte de 60 caixas de bebidas alcoólicas para a adega Vinho & Cia, Av. do Vinho, 357', '2024-05-15', 'CONCLUIDO'),
(14, 3, 'Entrega de 30 caixas de perfumes para a loja Fragrâncias, Rua das Aromas, 468', '2024-06-09', 'TRANSITANDO'),
(36, 7, 'Envio de 200kg de produtos para pets para a distribuidora PetLand, Av. dos Animais, 579', '2024-06-25', 'TRANSITANDO'),
(46, 1, 'Transporte de 20 pallets de peças automotivas para a loja AutoPeças, Rua do Carro, 680', '2024-07-14', 'AGUARDANDO'),
(5, 14, 'Entrega de 100kg de chocolates para a fábrica de doces Delícias do Coração, Av. dos Doces, 791', '2024-08-02', 'CONCLUIDO'),
(30, 6, 'Envio de 5 caixas de equipamentos esportivos para a loja Sport & Fitness, Rua do Esporte, 802', '2024-08-21', 'TRANSITANDO'),
(27, 10, 'Transporte de 50 toneladas de areia para a obra na Av. da Construção, 913', '2024-09-04', 'TRANSITANDO'),
(40, 12, 'Entrega de 200 caixas de velas aromáticas para a loja Luar & Aromas, Av. da Tradição, 104', '2024-10-14', 'TRANSITANDO'),
(1, 5, 'Envio de 10 pallets de livros didáticos para a escola Saber e Crescer, Rua do Aprendizado, 215', '2024-11-03', 'CONCLUIDO'),
(44, 9, 'Transporte de 100kg de flores para a floricultura Jardim dos Sonhos, Av. da Natureza, 326', '2024-11-12', 'TRANSITANDO'),
(16, 2, 'Entrega de 15 caixas de artigos de festa para a loja Festa e Cia, Rua da Alegria, 437', '2024-11-21', 'TRANSITANDO'),
(19, 1, 'Envio de 20 tonéis de suco para o restaurante Sucos Naturais, Av. das Bebidas, 548', '2024-12-02', 'TRANSITANDO'),
(33, 4, 'Transporte de 50 caixas de gadgets para a loja Tech World, Rua da Inovação, 659', '2024-12-10', 'AGUARDANDO'),
(10, 11, 'Entrega de 200kg de material para jardinagem para o paisagista Verdejar, Av. do Jardim, 760', '2024-12-15', 'TRANSITANDO'),
(25, 7, 'Envio de 5 pallets de brinquedos educativos para a loja Aprender Brincando, Rua da Educação, 871', '2024-12-24', 'AGUARDANDO'),
(45, 10, 'Transporte de 30 caixas de artigos de costura para a loja Costura & Cia, Av. do Artesanato, 982', '2025-01-05', 'AGUARDANDO'),
(2, 12, 'Entrega de 10 caixas de eletrônicos para a loja Digital Shop, Rua da Tecnologia, 103', '2025-01-14', 'AGUARDANDO'),
(24, 1, 'Envio de 150kg de frutas secas para o mercado Natural Fresh, Av. da Saúde, 214', '2025-01-28', 'AGUARDANDO'),
(38, 3, 'Transporte de 20 pallets de sacos de cimento para a construção na Rua dos Pedreiros, 325', '2025-02-02', 'AGUARDANDO'),
(23, 12, 'Entrega de 60 caixas de utensílios de escritório para a empresa Escritório Eficiente, Av. do Trabalho, 436', '2025-02-18', 'CANCELADO'),
(6, 3, 'Envio de 100kg de ingredientes para panificação para a padaria Pão Quente, Rua do Forno, 547', '2025-03-06', 'AGUARDANDO'),
(15, 2, 'Transporte de 40 caixas de produtos de beleza para a loja Belezura, Av. da Estética, 658', '2025-03-20', 'AGUARDANDO'),
(50, 11, 'Entrega de 5 tonéis de molho de tomate para a fábrica de conservas Sabor do Campo, Av. da Conserva, 769', '2025-04-04', 'AGUARDANDO'),
(28, 8, 'Envio de 150kg de produtos de higiene pessoal para a loja Higiene & Saúde, Rua do Bem-Estar, 870', '2025-04-11', 'AGUARDANDO'),
(41, 4, 'Transporte de 200kg de sementes para a cooperativa Agrícola, Av. do Campo, 981', '2025-04-26', 'AGUARDANDO'),
(20, 6, 'Entrega de 50 caixas de papelaria para a escola Arte & Papel, Rua da Criatividade, 109', '2025-05-03', 'AGUARDANDO'),
(7, 11, 'Envio de 30 pacotes de produtos de limpeza para a empresa Limpeza Ágil, Av. da Limpeza, 210', '2025-05-15', 'AGUARDANDO'),
(32, 14, 'Transporte de 10 pallets de material para construção para a obra na Rua dos Engenheiros, 321', '2025-05-22', 'AGUARDANDO'),
(26, 15, 'Entrega de 200kg de chocolates artesanais para a loja Doce Sabor, Av. dos Doces, 432', '2025-05-29', 'AGUARDANDO'),
(13, 9, 'Envio de 60 caixas de acessórios para celulares para a loja Mobile Store, Rua da Tecnologia, 543', '2025-01-03', 'AGUARDANDO'),
(35, 5, 'Transporte de 15 pallets de móveis planejados para a loja Planeje Seu Espaço, Av. do Lar, 654', '2025-02-07', 'AGUARDANDO'),
(48, 3, 'Entrega de 50kg de especiarias para o restaurante Sabores do Mundo, Rua da Culinária, 765', '2025-02-22', 'AGUARDANDO'),
(18, 10, 'Envio de 30 caixas de cosméticos naturais para a loja Natureza Pura, Av. da Beleza, 876', '2025-03-15', 'AGUARDANDO'),
(9, 12, 'Transporte de 100kg de frutas frescas para o mercado Saúde do Campo, Rua da Horta, 987', '2025-03-29', 'AGUARDANDO'),
(47, 2, 'Entrega de 10 tonéis de vinagre para a indústria de conservas, Av. do Sabor, 123', '2025-04-14', 'AGUARDANDO'),
(39, 14, 'Envio de 200kg de verduras para o restaurante Verde e Fresco, Rua da Alimentação, 234', '2025-05-10', 'AGUARDANDO'),
(14, 1, 'Transporte de 50 pacotes de café para a cafeteria Café do Ponto, Av. do Aroma, 345', '2025-05-20', 'AGUARDANDO'),
(21, 7, 'Entrega de 40 caixas de roupas infantis para a loja Kids & Cia, Rua da Infância, 456', '2025-06-01', 'AGUARDANDO');
Go;

--Verificando registros
select * from Drivers;
select * from Clients;
select * from Orders;

--Deletando pedido para existir clientes que não realizaram pedidos
DELETE FROM Orders WHERE ClientID = 37;

-- Atualizaando o telefone do motorista
select Nome, Contato from Drivers where DriverID = 8;
UPDATE Drivers set Contato = '45985371703' where DriverID = 8;
select Nome, Contato from Drivers;

--clientes que ainda não efetuaram pedidos
select C.ClientID, c.Nome, o.OrderID from Clients C
left join Orders o on c.ClientID = o.ClientID
where o.OrderID is null;

--motoristas que ainda não trabalharam pela empresa
select * from Drivers where not exists (select distinct 1 from Orders where orders.DriverID = Drivers.DriverID);

--Pedidos cancelados com detalhes do cliente e motorista
select o.OrderID, o.DetalhesPedido, c.Empresa, d.Nome, o.DataEntrega from Orders o 
inner join Clients c on o.ClientID = c.ClientID 
inner join Drivers d on o.DriverID = d.DriverID where o.Status = 'CANCELADO';


--Pedidos que não foram iniciados ou concluidos com detalhes do cliente e motorista
select o.OrderID, o.DetalhesPedido, c.Empresa, d.Nome, o.DataEntrega from Orders o
inner join Clients c on o.ClientID = c.ClientID
inner join Drivers d on o.DriverID = d.DriverID
where o.Status = 'AGUARDANDO'
ORDER by o.DataEntrega;

--Numero de pedidos de cada motorista
select COUNT(O.DriverID) as Pedidos, d.Nome from Orders o
inner join Drivers d on o.DriverID = d.DriverID
where o.Status != 'CANCELADO'
GROUP BY O.DriverID, D.Nome
order by Pedidos desc;

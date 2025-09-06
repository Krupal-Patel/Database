USE GuitarOwnership;

CREATE TABLE Owners(           
    owner_id int PRIMARY KEY,
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100),
    birthdate datetime NOT NULL);
    
CREATE TABLE Dealers(
    dealer_id int PRIMARY KEY,
    dealer varchar(200) NOT NULL,
    dealer_city varchar(100) NOT NULL);
    
CREATE TABLE Manufacturers(
    manufacturer_id int PRIMARY KEY,
    manufacturer_name VARCHAR(100) NOT NULL);
    
CREATE TABLE Guitar_Types(
    guitar_type_id int,
    guitar_type VARCHAR(100) NOT NULL)

ALTER TABLE Guitar_Types
    ADD PRIMARY KEY (guitar_type_id);
    
CREATE TABLE Models(
    model_name VARCHAR(100) NOT NULL,
    manufacturer_id int NOT NULL,
    guitar_type_id int NOT NULL,
    CONSTRAINT PK_Models 
        PRIMARY KEY (model_name),
    CONSTRAINT FK_Models_Manufacturers
        FOREIGN KEY (manufacturer_id)
        REFERENCES Manufacturers (manufacturer_id),
    CONSTRAINT FK_Models_Guitar_Types
        FOREIGN KEY (guitar_type_id)
        REFERENCES Guitar_Types (guitar_type_id)
    );

CREATE INDEX IDX_manufacturer_id 
    ON Models (manufacturer_id);
    
CREATE INDEX IDX_guitar_type_id
    ON Models (guitar_type_id);
    
CREATE TABLE Guitars(
    guitar_id int,
    model_name VARCHAR(100),
    CONSTRAINT PK_Guitars 
        PRIMARY KEY (guitar_id),
    CONSTRAINT FK_Guitars_Models 
        FOREIGN KEY (model_name)
        REFERENCES Models(model_name));

CREATE INDEX IDX_model_name 
    ON Guitars (model_name);
    
CREATE TABLE CustomerGuitar(
    owner_id INT,
    guitar_id INT,
    price float,
    dealer_id INT,
    CONSTRAINT PK_CustomerGuitar
        PRIMARY KEY (owner_id, guitar_id),
    CONSTRAINT FK_CustomerGuitar_Guitars
        FOREIGN KEY (guitar_id)
        REFERENCES Guitars (guitar_id),
    CONSTRAINT FK_CustomerGuitar_Owners
        FOREIGN KEY (owner_id)
        REFERENCES Owners (owner_id),
    CONSTRAINT FK_CustomerGuitar_Dealers
        FOREIGN KEY (dealer_id)
        REFERENCES Dealers (dealer_id));

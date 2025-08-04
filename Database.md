<h1>DATABASE COMMANDS </h1>   

                    show databases;
                    create database database name;

                    use database_name;

                    CREATE TABLE IF NOT EXISTS users (
                    id INT AUTO_INCREMENT PRIMARY KEY,
                    name VARCHAR(100) NOT NULL,
                    email VARCHAR(100) NOT NULL,
                    website VARCHAR(100),
                    comment TEXT,
                    gender ENUM('male', 'female', 'other') NOT NULL,
                    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
                    );

                    
                

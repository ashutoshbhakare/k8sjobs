kubectl exec -it <mysql-pod-name> -- mysql -u root -pcentos 

CREATE DATABASE unnati;
USE unnati;

CREATE TABLE student (
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(50)
);

INSERT INTO student (name) VALUES 
('Rahul Sharma'), 
('Amit Verma'), 
('Rohit Sharma'), 
('Priya Singh'), 
('Sneha Patil'), 
('Vikram Rathore'), 
('Anjali Gupta'), 
('Rohan Deshmukh'), 
('Kavita Reddy'), 
('Sameer Khan'), 
('Pooja Joshi'), 
('Manish Malhotra'), 
('Sunita Williams'), 
('Arjun Kapoor'), 
('Neha Kakkar');

EXIT; 

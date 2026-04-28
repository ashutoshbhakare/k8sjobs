## Command to get into pod
kubectl exec -it <mysql-pod-name> -- mysql -u root -pcentos 

## Lets create DB and Tables 
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


## Verify Backup 

kubectl logs job/mysql-backup-job

ssh  node01
cat /opt/mysql-backups/unnati.sql
grep -i "student" /opt/mysql-backups/unnati.sql



## Restore Job 

kubectl exec -it <mysql-pod-name> -- mysql -u root -pcentos 

First delete data manually (to test restore):

DROP DATABASE unnati;

## Check data:

kubectl exec -it <mysql-pod-name> -- mysql -u root -pcentos

USE unnati;
SELECT * FROM student;

CREATE DATABASE unnati;
EXIT;


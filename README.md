# git-test
This repository is used to test git scripting


CREATE TABLE Client_Report_Options (
    option_id BIGINT IDENTITY(1,1) PRIMARY KEY,
    client_id VARCHAR(50) NOT NULL,
    report_id BIGINT NOT NULL,
    receive_flag BIT NOT NULL,
    output_type_cd INT NOT NULL,
    file_type_cd INT NOT NULL,
    email_flag INT NOT NULL,
    report_password_tx VARCHAR(255),
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    updated_at DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    FOREIGN KEY (report_id) REFERENCES admin_query_list(report_id)
);



CREATE TABLE admin_query_list (
    report_id BIGINT IDENTITY(1,1) PRIMARY KEY,
    report_name VARCHAR(255) NOT NULL,
    report_by_client_flag BIT NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    updated_at DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);


CREATE TABLE client_email (
    id BIGINT IDENTITY(1,1) PRIMARY KEY,
    Client_ID VARCHAR(50) NOT NULL,
    Report_ID BIGINT NOT NULL,
    Email_Name_tx VARCHAR(255) NOT NULL,
    Email_Address_tx VARCHAR(255) NOT NULL,
    Carbon_Copy_Flag BIT NOT NULL,
    Active_Flag BIT NOT NULL,
    Mail_Server_ID BIGINT NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    updated_at DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);


SELECT Vend_id, Vend_nm, Vend_rcvr_cd, Vend_fsrv_nm, Vend_fsrv_ip
FROM VENDOR
WHERE VEND_ACTV_CD = 1 and Vend_file_IO = 'XML'

 







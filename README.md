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


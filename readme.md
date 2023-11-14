<h1 align="center">Ngeureuyeuh Webpac CI 4</h1>

<p align="center">
<img src="https://lib.itb.ac.id/wp-content/uploads/sites/163/2021/08/logo-lib-2-scaled-e1628143079354.png">
</p>

## Project setup

```
ALTER TABLE `staff_privileges` CHANGE `fileAccessed` `fileAccessed` TEXT CHARACTER SET latin1 COLLATE latin1_swedish_ci NULL DEFAULT NULL;
INSERT INTO `staff_privileges` (`privilegesID`, `staffGroupID`, `fileAccessed`) VALUES (NULL, '1', 'dashboard;reloan;sirkulasi;bibliografi;ill;matakuliah;usulan;procurement;pengguna;other;');
```

```
DROP TABLE IF EXISTS `ci_sessions`;
CREATE TABLE `ci_sessions` (
`id` varchar(128) NOT NULL,
`ip_address` varchar(45) NOT NULL,
`timestamp` timestamp NOT NULL DEFAULT current_timestamp(),
`data` blob NOT NULL,
PRIMARY KEY (`id`,`ip_address`),
UNIQUE KEY `id_UNIQUE` (`id`),
KEY `ci_sessions_timestamp` (`timestamp`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
```

Check the [official site](https://codeigniter.com/user_guide/libraries/sessions.html#databasehandler-driver).

### Template Config

Template baru untuk dashboard admin
Check the documentation [here](https://preview.keenthemes.com/html/metronic/docs/index).

### Path Config

- **SSO ITB** 
  - Config `[CasCon.php]`
  - Libraries `phpCAS-1.3.7` `[Cas.php]`
    
- **Autentifikasi Login dan Modul Akses** 
  - Config `[Filters.php]`
  - Filters `[AuthGuard.php]` `[RedirectIfAuthGuard.php]`
 
- **Snippet Theme and function** 
  - Helpers `[theme_helper.php]` `[union_helper.php]`

- **All Config Structure**
  - Config `[Union.php]`

# Progress Modul
## Sirkulasi
### Loan
- Index, Proses, Detail (&#10003;)
- Reloan (&#10003;) :: ada catatan di model
- bp (&#10003;)
- loanMail (&#10003;) :: ada error settings :: cek runmail_log
- in_reloan_staf (&#10003;)
- tutup_kasus
- loanList [superuser]
- loanlist detail [superuser]

---
title: Instalar SQL Server Integration Services en Linux | Documentos de Microsoft
description: En este artículo se describe cómo instalar SQL Server Integration Services (SSIS) en Linux.
author: leolimsft
ms.author: lle
ms.reviewer: douglasl
manager: craigg
ms.date: 01/09/2018
ms.topic: article
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: ''
ms.suite: sql
ms.custom: sql-linux
ms.technology: database-engine
ms.workload: On Demand
ms.openlocfilehash: 79ea78bc8697c477968f2a1b7dba6e90e689b54d
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="install-sql-server-integration-services-ssis-on-linux"></a>Instalar SQL Server Integration Services (SSIS) en Linux

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

Siga los pasos de este artículo para instalar SQL Server Integration Services (`mssql-server-is`) en Linux. Para obtener información sobre las características admitidas en esta versión de servicios de integración para Linux, consulte la [notas de la versión](sql-server-linux-release-notes.md).

Instalar a servidores de integración de SQL Server para su plataforma:

- [Ubuntu](#ubuntu)
- [Red Hat Enterprise Linux](#RHEL)

## <a name="ubuntu"></a> Instalar SSIS en Ubuntu
Para instalar el `mssql-server-is` el paquete en Ubuntu, siga estos pasos:

1. Importar las claves GPG repositorio público.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
   ```

2. Registrar el repositorio de Microsoft SQL Server Ubuntu.

   ```bash
   sudo add-apt-repository "$(curl https://packages.microsoft.com/config/ubuntu/16.04/mssql-server-2017.list)"
   ```

3. Ejecute los comandos siguientes para instalar SQL Server Integration Services.

   ```bash
   sudo apt-get update
   sudo apt-get install -y mssql-server-is
   ```

4. Después de instalar Integration Services, ejecutar `ssis-conf`. Para obtener más información, consulte [configurar SSIS en Linux con ssis-conf](sql-server-linux-configure-ssis.md).

   ```bash
   sudo /opt/ssis/bin/ssis-conf setup
   ```

5. Después de realiza la configuración, establezca la ruta de acceso.

   ```bash
   export PATH=/opt/ssis/bin:$PATH
   ```

### <a name="update-ssis"></a>Actualización de SSIS
Si ya tiene `mssql-server-is` instalado, puede actualizar a la versión más reciente con el siguiente comando:

```bash
sudo apt-get install mssql-server-is
```

### <a name="remove-ssis"></a>Quitar SSIS
Para quitar `mssql-server-is`, puede ejecutar el comando siguiente:
```bash
sudo apt-get remove mssql-server-is
```

## <a name="RHEL"></a> Instalar SSIS en RHEL
Para instalar el `mssql-server-is` el paquete en RHEL, siga estos pasos:

1. Descargue el archivo de configuración del repositorio de Microsoft SQL Server Red Hat.

   ```bash
   sudo curl -o /etc/yum.repos.d/mssql-server.repo https://packages.microsoft.com/config/rhel/7/mssql-server-2017.repo
   ```

1. Ejecute los comandos siguientes para instalar SQL Server Integration Services.

   ```bash
   sudo yum install -y mssql-server-is
   ```


1. Después de la instalación, ejecute `ssis-conf`. Para obtener más información, consulte [configurar SSIS en Linux con ssis-conf](sql-server-linux-configure-ssis.md).

   ```bash
   sudo /opt/ssis/bin/ssis-conf setup
   ```

1. Una vez que se realiza la configuración, establezca la ruta de acceso.

   ```bash
   export PATH=/opt/ssis/bin:$PATH
   ```

### <a name="update-ssis"></a>Actualización de SSIS
Si ya tiene `mssql-server-is` instalado, puede actualizar a la versión más reciente con el siguiente comando:

```bash
sudo yum update mssql-server-is
```

### <a name="remove-ssis"></a>Quitar SSIS
Para quitar `mssql-server-is`, puede ejecutar el comando siguiente:
```bash
sudo yum remove mssql-server-is
```

## <a name="unattended-installation"></a>Instalación desatendida
Para ejecutar una instalación desatendida cuando se ejecuta `ssis-conf setup`, haga lo siguiente:
1.  Especifique el `-n` (sin preguntar) opción.
2.  Proporcionar los valores necesarios mediante el establecimiento de variables de entorno.

En el ejemplo siguiente se hace lo siguiente:
-   Instala SSIS.
-   Especifica la edición Developer, proporcionando un valor para el `SSIS_PID` variable de entorno.
-   Acepta los términos de licencia proporcionando un valor para el `ACCEPT_EULA` variable de entorno.
-   Se ejecuta una instalación desatendida mediante la especificación de la `-n` (sin preguntar) opción.

```
sudo SSIS_PID=Developer ACCEPT_EULA=Y /opt/ssis/bin/ssis-conf -n setup 
```

### <a name="environment-variables-for-unattended-installation"></a>Variables de entorno para la instalación desatendida

| Variable de entorno | Description |
|---|---|
| **ACCEPT_EULA** | Acepta el contrato de licencia de SQL Server cuando se establece en cualquier valor (por ejemplo, `Y`).|
| **SSIS_PID** | Establece la clave de producto o de edición de SQL Server. Estos son los valores posibles:<br/>Evaluation<br/>Desarrollador<br/>Express <br/>Web <br/>Standard<br/>Enterprise <br/>Una clave de producto<br/><br/>Si especifica una clave de producto, la clave del producto debe tener la forma `#####-#####-#####-#####-#####`, donde `#` es una letra o un número.  |
| | |

## <a name="next-steps"></a>Pasos siguientes

Para ejecutar paquetes SSIS en Linux, consulte [extracción, transformación y carga de datos para SQL Server en Linux con SSIS](sql-server-linux-migrate-ssis.md).

Para configurar opciones adicionales de SSIS en Linux, consulte [configurar SQL Server Integration Services en Linux con ssis-conf](sql-server-linux-configure-ssis.md).

## <a name="related-content-about-ssis-on-linux"></a>Contenido relacionado sobre SSIS en Linux
-   [Extraer, transformar y cargar datos en Linux con SSIS](sql-server-linux-migrate-ssis.md)
-   [Configurar SQL Server Integration Services en Linux con ssis-conf](sql-server-linux-configure-ssis.md)
-   [Limitaciones y problemas conocidos de SSIS en Linux](sql-server-linux-ssis-known-issues.md)
-   [Ejecución en Linux con cron del paquete de programación de SQL Server Integration Services](sql-server-linux-schedule-ssis-packages.md)

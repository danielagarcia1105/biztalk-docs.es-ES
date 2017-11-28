---
title: Conectarse a SQL Server Always Encrypted columnas con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fcc20a2b-daf9-4b7f-ae61-cb408e4bd04c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e117bd91176589e998fc01eb2c613ac0da2bbc
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a>Conectarse a SQL Server Always Encrypted columnas con BizTalk Server
Habilitar Always Encrypted en el adaptador de WCF-SQL en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] para consultar columnas cifradas.  

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , el adaptador de WCF-SQL puede consultar columnas cifradas en [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]. El `ColumnEncryptionSetting` enlaza la propiedad se utiliza para habilitar o deshabilitar la funcionalidad para obtener los valores de columna cifrado/descifrado de una base de datos Always Encrypted.

Este tema muestra cómo habilitar o deshabilitar esta característica en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

> [!TIP] 
> [Always Encrypted (motor de base de datos)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) es un excelente recurso para comprender y obtener más información sobre esto [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] característica.

## <a name="prerequisites"></a>Requisitos previos
Instalar [Feature Pack 2](https://aka.ms/bts2016fp2) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

## <a name="enable-always-encrypted"></a>Habilitar Always Encrypted

1. En el **administración de BizTalk Server** de la consola, haga clic en el puerto de WCF-SQL y seleccione **propiedades**.
2. Vaya a la **enlace** ficha.
3. En **Always Encrypted**, habilitar o deshabilitar la `ColumnEncryptionSettings` propiedad:

* **Habilitado**: las consultas de puerto y obtiene los datos cifrados de una base de datos Always Encrypted
* **Deshabilitado**: el puerto de consulta a la base de datos siempre se cifran, pero los datos devueltos se aplica un algoritmo hash

    ![Habilitar Always Encrypted](../core/media/enable-always-encrypted.png)

4. Seleccione **aplicar**, y **Aceptar** para guardar los cambios.

## <a name="see-also"></a>Vea también
[Always Encrypted (motor de base de datos)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[Configurar el Feature Pack](../core/configure-the-feature-pack.md)
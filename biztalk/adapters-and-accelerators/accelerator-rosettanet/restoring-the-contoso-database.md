---
title: Restaurar la base de datos de Contoso | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, restoring databases
- databases, restoring
ms.assetid: 291178c1-826e-49e0-a1d2-cbffee749659
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c242fe6477baac53b6a3e1b2fda545a7e4365
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-contoso-database"></a>Restaurar la base de datos de Contoso
En este paso, usa SQL Server Management Studio para ejecutar un script SQL para restaurar la base de datos de Contoso y sus procedimientos almacenados asociados. También rellena las tablas de base de datos con datos preliminares.  
  
### <a name="to-restore-the-contoso-database"></a>Para restaurar la base de datos de Contoso  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el cuadro de diálogo servidor, conectar con en el **SQL Server** cuadro, haga clic en **conectar**.  
  
    > [!NOTE]
    >  Si el Agente SQL Server no está iniciado, haga clic con el botón secundario sobre él y después haga clic en **Iniciar**.  
  
3.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4.  En el panel de consulta, copie y pegue el siguiente script SQL en la ventana de consulta:  
  
    ```  
    CREATE DATABASE Contoso  
    GO  
    USE Contoso  
    GO  
    CREATE TABLE Products (  
    [ProductID] [varchar] (255) NOT NULL ,  
    [Name] [varchar] (255) NOT NULL ,  
    [Description] [varchar] (800) NULL ,  
    [Price] [money] NULL ,  
    [NumberAvailable] [int] NOT NULL   
    ) ON [PRIMARY]  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901234', 'ADM Line Card','',200.65,820 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901235','Analog Line Card','',165.24,769 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901236', 'Mapper/MUX','',150.54,948)  
    GO  
    CREATE TABLE StatusCodes (  
    [statusID] [int] NOT NULL ,  
    [statusCode] [nvarchar] (50) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    CREATE PROCEDURE GetInventoryForProductID  
    @ProductID varchar(255),  
    @NumberAvailable INT OUTPUT,  
    @Price MONEY OUTPUT  
    AS  
    SET NOCOUNT ON  
    SELECT @NumberAvailable = NumberAvailable,  
     @Price = Price  
    FROM Products  
    WHERE  ProductID = @ProductID  
    RETURN(0)  
    GO  
    CREATE PROCEDURE SP_GetInventoryForProductID  
    @ProductID varchar(255)  
    AS  
    SET NOCOUNT ON  
    SELECT *  
    FROM Products  
    WHERE ProductID = @ProductID  
    for xml auto  
    RETURN(0)  
    ```  
  
5.  Haga clic en **Ejecutar**.  
  
### <a name="to-set-permissions-on-the-contoso-database"></a>Para establecer permisos en la base de datos de Contoso  
  
1.  En el Explorador de objetos de Microsoft SQL Server Management Studio, expanda **bases de datos**, expanda la **Contoso** base de datos y, a continuación, expanda **seguridad**. Haga clic con el botón secundario en **Usuarios**y después en **Usuario nuevo**.  
  
2.  En el usuario de base de datos - cuadro de diálogo nuevo, para **nombre de inicio de sesión**, haga clic en el botón de puntos suspensivos.  
  
3.  En el cuadro de diálogo Seleccionar inicio de sesión, haga clic en **examinar**.  
  
4.  En el cuadro de diálogo objetos buscar, seleccione **usuarios de la aplicación de BizTalk**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el cuadro de diálogo Seleccionar inicio de sesión, haga clic en **Aceptar**.  
  
6.  En el usuario de base de datos - nuevo cuadro de diálogo, en la **pertenencia al rol de base de datos** panel, seleccione **db_datareader** y **db_datawriter**. Para **nombre de usuario**, escriba **usuarios de la aplicación de BizTalk**. Haga clic en **Aceptar**.  
  
7.  Repita los pasos del 1 al 6 para **usuarios de hosts aislados de BizTalk**, seleccione **db_datareader** y **db_datawriter** para **miembrosdelroldebasededatos**y escriba **usuarios de hosts aislados de BizTalk** para **nombre de usuario**.  
  
8.  Repita los pasos del 1 al 6 para **administradores de BizTalk Server**, seleccione **db_owner** para **pertenencia al rol de base de datos**y escriba **BizTalk Server Los administradores** para **nombre de usuario**.  
  
## <a name="see-also"></a>Vea también  
 [Generar y habilitar certificados](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)
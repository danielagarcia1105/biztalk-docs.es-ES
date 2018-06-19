---
title: Restaurar la base de datos de Contoso | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, restoring databases
- databases, restoring
ms.assetid: 291178c1-826e-49e0-a1d2-cbffee749659
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c242fe6477baac53b6a3e1b2fda545a7e4365
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210228"
---
# <a name="restoring-the-contoso-database"></a><span data-ttu-id="0d06c-102">Restaurar la base de datos de Contoso</span><span class="sxs-lookup"><span data-stu-id="0d06c-102">Restoring the Contoso Database</span></span>
<span data-ttu-id="0d06c-103">En este paso, usa SQL Server Management Studio para ejecutar un script SQL para restaurar la base de datos de Contoso y sus procedimientos almacenados asociados.</span><span class="sxs-lookup"><span data-stu-id="0d06c-103">In this step, you use SQL Server Management Studio to run a SQL script to restore the Contoso database and its associated stored procedures.</span></span> <span data-ttu-id="0d06c-104">También rellena las tablas de base de datos con datos preliminares.</span><span class="sxs-lookup"><span data-stu-id="0d06c-104">You also populate the database tables with preliminary data.</span></span>  
  
### <a name="to-restore-the-contoso-database"></a><span data-ttu-id="0d06c-105">Para restaurar la base de datos de Contoso</span><span class="sxs-lookup"><span data-stu-id="0d06c-105">To restore the Contoso database</span></span>  
  
1.  <span data-ttu-id="0d06c-106">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="0d06c-107">En el cuadro de diálogo servidor, conectar con en el **SQL Server** cuadro, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-107">In the Connect to Server dialog box, in the **SQL Server** box, click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d06c-108">Si el Agente SQL Server no está iniciado, haga clic con el botón secundario sobre él y después haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-108">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="0d06c-109">En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-109">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="0d06c-110">En el panel de consulta, copie y pegue el siguiente script SQL en la ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="0d06c-110">In the Query pane, copy and paste the following SQL script into the Query window:</span></span>  
  
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
  
5.  <span data-ttu-id="0d06c-111">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-111">Click **Execute**.</span></span>  
  
### <a name="to-set-permissions-on-the-contoso-database"></a><span data-ttu-id="0d06c-112">Para establecer permisos en la base de datos de Contoso</span><span class="sxs-lookup"><span data-stu-id="0d06c-112">To set permissions on the Contoso database</span></span>  
  
1.  <span data-ttu-id="0d06c-113">En el Explorador de objetos de Microsoft SQL Server Management Studio, expanda **bases de datos**, expanda la **Contoso** base de datos y, a continuación, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-113">In the Object Explorer of the Microsoft SQL Server Management Studio, expand **Databases**, expand the **Contoso** database, and then expand **Security**.</span></span> <span data-ttu-id="0d06c-114">Haga clic con el botón secundario en **Usuarios**y después en **Usuario nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-114">Right-click **Users**, and then click **New User**.</span></span>  
  
2.  <span data-ttu-id="0d06c-115">En el usuario de base de datos - cuadro de diálogo nuevo, para **nombre de inicio de sesión**, haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="0d06c-115">In the Database User - New dialog box, for **Login name**, click the ellipsis.</span></span>  
  
3.  <span data-ttu-id="0d06c-116">En el cuadro de diálogo Seleccionar inicio de sesión, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-116">In the Select Login dialog box, click **Browse**.</span></span>  
  
4.  <span data-ttu-id="0d06c-117">En el cuadro de diálogo objetos buscar, seleccione **usuarios de la aplicación de BizTalk**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-117">In the Browse for Objects dialog box, select **BizTalk Application Users**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="0d06c-118">En el cuadro de diálogo Seleccionar inicio de sesión, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-118">In the Select Login dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="0d06c-119">En el usuario de base de datos - nuevo cuadro de diálogo, en la **pertenencia al rol de base de datos** panel, seleccione **db_datareader** y **db_datawriter**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-119">In the Database User - New dialog box, in the **Database role membership** pane, select **db_datareader** and **db_datawriter**.</span></span> <span data-ttu-id="0d06c-120">Para **nombre de usuario**, escriba **usuarios de la aplicación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-120">For **User name**, enter **BizTalk Application Users**.</span></span> <span data-ttu-id="0d06c-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-121">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0d06c-122">Repita los pasos del 1 al 6 para **usuarios de hosts aislados de BizTalk**, seleccione **db_datareader** y **db_datawriter** para **miembrosdelroldebasededatos**y escriba **usuarios de hosts aislados de BizTalk** para **nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-122">Repeat steps 1 through 6 for **BizTalk Isolated Host Users**, selecting **db_datareader** and **db_datawriter** for **Database role membership**, and entering **BizTalk Isolated Host Users** for **User name**.</span></span>  
  
8.  <span data-ttu-id="0d06c-123">Repita los pasos del 1 al 6 para **administradores de BizTalk Server**, seleccione **db_owner** para **pertenencia al rol de base de datos**y escriba **BizTalk Server Los administradores** para **nombre de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0d06c-123">Repeat steps 1 through 6 for **BizTalk Server Administrators**, selecting **db_owner** for **Database role membership**, and entering **BizTalk Server Administrators** for **User name**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d06c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d06c-124">See Also</span></span>  
 [<span data-ttu-id="0d06c-125">Generar y habilitar certificados</span><span class="sxs-lookup"><span data-stu-id="0d06c-125">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)
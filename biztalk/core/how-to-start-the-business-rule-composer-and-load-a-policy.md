---
title: Cómo iniciar el Compositor de reglas de negocio y cargar una directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56d3d2c1dde771d86f8de345d6e3b249ab394b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977053"
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a><span data-ttu-id="1e246-102">Cómo iniciar el Compositor de reglas de negocio y cargar una directiva</span><span class="sxs-lookup"><span data-stu-id="1e246-102">How to Start the Business Rule Composer and Load a Policy</span></span>
<span data-ttu-id="1e246-103">En esta sección se describe cómo iniciar el Compositor de reglas de negocio y cargar una directiva.</span><span class="sxs-lookup"><span data-stu-id="1e246-103">This section describes how to start the Business Rule Composer and load a policy.</span></span>  
  
### <a name="to-start-the-business-rule-composer"></a><span data-ttu-id="1e246-104">Para iniciar el Compositor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="1e246-104">To start the Business Rule Composer</span></span>  
  
- <span data-ttu-id="1e246-105">En el **iniciar** menú, elija **todos los programas**, señale Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, haga clic en **compositor**.</span><span class="sxs-lookup"><span data-stu-id="1e246-105">On the **Start** menu, point to **All Programs**, point to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **Business Rule Composer**.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1e246-106">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="1e246-106">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="1e246-107">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1e246-107">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
### <a name="to-load-a-policy"></a><span data-ttu-id="1e246-108">Para cargar una directiva</span><span class="sxs-lookup"><span data-stu-id="1e246-108">To load a policy</span></span>  
  
1.  <span data-ttu-id="1e246-109">En el Compositor de reglas de negocio, en el **regla Store** menú, haga clic en **carga**.</span><span class="sxs-lookup"><span data-stu-id="1e246-109">In the Business Rule Composer, on the **Rule Store** menu, click **Load**.</span></span>  
  
2.  <span data-ttu-id="1e246-110">En el **regla Store** cuadro de diálogo el **SQL Server** lista desplegable, seleccione el equipo SQL Server™ a la que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="1e246-110">In the **Rule Store** dialog box, in the **SQL Server** drop-down list, select the SQL Server™ computer to which you want to connect.</span></span>  
  
3.  <span data-ttu-id="1e246-111">En el **base de datos** lista desplegable, seleccione la base de datos que contiene el almacén de reglas que desea abrir.</span><span class="sxs-lookup"><span data-stu-id="1e246-111">In the **Database** drop-down list, select the database that contains the rule store you want to open.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e246-112">La base de datos predeterminada para el almacén de reglas que se instala de forma [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es **BizTalkRuleEngineDb**.</span><span class="sxs-lookup"><span data-stu-id="1e246-112">The default database for the rule store installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is **BizTalkRuleEngineDb**.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="1e246-113">Si usa una cuenta de SQL Server recién creada que tenga el **exigir expiración de contraseña** y **usuario debe cambiar la contraseña en el siguiente inicio de sesión** conjunto de opciones, el Compositor de reglas de negocios se podrá conectar a la regla Base de datos del motor.</span><span class="sxs-lookup"><span data-stu-id="1e246-113">If you use a newly created SQL Server account that has the **Enforce password expiration** and **User must change password at next login** options set, the business rule composer will fail to connect to the Rule Engine database.</span></span>
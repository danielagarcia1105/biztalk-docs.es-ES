---
title: Cómo importar y exportar directivas y vocabularios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb235d126ca775cc8bd5a752388c948a2203e4b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968845"
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a><span data-ttu-id="a7435-102">Cómo importar y exportar directivas y vocabularios</span><span class="sxs-lookup"><span data-stu-id="a7435-102">How to Import and Export Policies and Vocabularies</span></span>
<span data-ttu-id="a7435-103">Puede usar el Asistente para implementar el motor de reglas para importar o exportar una directiva o vocabulario.</span><span class="sxs-lookup"><span data-stu-id="a7435-103">You can use the Rules Engine Deployment Wizard to import or export a policy or vocabulary.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a7435-104">En primer lugar deben importarse todos los vocabularios que utilicen una directiva o vocabulario o se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a7435-104">All vocabularies used by a policy or vocabulary must be imported first or you will get an error.</span></span>  

### <a name="to-import-or-export-a-policy-or-vocabulary"></a><span data-ttu-id="a7435-105">Para importar o exportar una directiva o vocabulario</span><span class="sxs-lookup"><span data-stu-id="a7435-105">To import or export a policy or vocabulary</span></span>  

1. <span data-ttu-id="a7435-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente para implementación de motor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="a7435-106">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7435-107">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a7435-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="a7435-108">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a7435-108">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2. <span data-ttu-id="a7435-109">En la página de bienvenida, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7435-109">On the welcome page, click **Next**.</span></span>  

3. <span data-ttu-id="a7435-110">En el **tarea de implementación** página, seleccione **Exportar directiva o vocabulario a archivo de base de datos** o **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, Haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7435-110">On the **Deployment Task** page, select either **Export Policy/Vocabulary to file from database** or **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  

4. <span data-ttu-id="a7435-111">En el **directiva Store** página, en las listas desplegables, seleccione un equipo de SQL Server disponible y base de datos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7435-111">On the **Policy Store** page, from the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  

5. <span data-ttu-id="a7435-112">En el **Exportar directiva o vocabulario** página, haga lo siguiente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7435-112">On the **Export Policy/Vocabulary** page, do the following, and then click **Next**.</span></span>  

   1.  <span data-ttu-id="a7435-113">Seleccione **directiva** o **vocabulario** dependiendo de lo que desea exportar o importar.</span><span class="sxs-lookup"><span data-stu-id="a7435-113">Select **Policy** or **Vocabulary** depending on what you want to export/import.</span></span>  

   2.  <span data-ttu-id="a7435-114">Desde el **directiva o vocabulario** lista desplegable, seleccione la directiva o vocabulario deseado.</span><span class="sxs-lookup"><span data-stu-id="a7435-114">From the **Policy/Vocabulary** drop-down list, select the desired policy/vocabulary.</span></span>  

   3.  <span data-ttu-id="a7435-115">Haga clic en **examinar** para seleccionar el archivo de definición.</span><span class="sxs-lookup"><span data-stu-id="a7435-115">Click **Browse** to select the definition file.</span></span>  

6. <span data-ttu-id="a7435-116">Revise el servidor, base de datos y la información de directiva o vocabulario y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7435-116">Review the server, database, and policy or vocabulary information, and then click **Next**.</span></span>  

7. <span data-ttu-id="a7435-117">Una vez completada la importación o exportación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7435-117">After the import or export is completed, click **Next**.</span></span>  

8. <span data-ttu-id="a7435-118">Revise el estado de finalización de la importación o exportación y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a7435-118">Review the completion status of the import or export, and then click **Finish**.</span></span>

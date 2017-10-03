---
title: Crear un proyecto de esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58017b24f7b7464745f48cc202734217dfb327d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-schema-project"></a><span data-ttu-id="27df0-102">Crear un proyecto de esquema</span><span class="sxs-lookup"><span data-stu-id="27df0-102">Creating a Schema Project</span></span>
<span data-ttu-id="27df0-103">Para crear un proyecto de esquema:</span><span class="sxs-lookup"><span data-stu-id="27df0-103">To create a schema project:</span></span>  
  
1.  <span data-ttu-id="27df0-104">En Visual Studio, cree el proyecto de BizTalk de esquema de SWIFT MX.</span><span class="sxs-lookup"><span data-stu-id="27df0-104">In Visual Studio, create the SWIFT MX Schema BizTalk project.</span></span>  
  
2.  <span data-ttu-id="27df0-105">Agregue el esquema apropiado MX (descargado desde el sitio de ISO20022), que desea probar, a este proyecto.</span><span class="sxs-lookup"><span data-stu-id="27df0-105">Add the appropriate MX schema (downloaded from ISO20022 site), which you wish to test, to this project.</span></span>  
  
3.  <span data-ttu-id="27df0-106">Si desea ejecutar la funcionalidad de reparación de mensajes y nuevo envío para el mensaje de MX anterior, un esquema de sobre que corresponde al tipo de mensaje anterior también debe implementarse else vaya al paso 6.</span><span class="sxs-lookup"><span data-stu-id="27df0-106">If you want to execute the Message Repair and New Submission functionality for the above MX message, then an Envelope schema corresponding to the above message type also needs to be deployed else proceed to step 6.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27df0-107">Para obtener información sobre cómo generar esquemas de sobres de MX, consulte la documentación del generador de formulario.</span><span class="sxs-lookup"><span data-stu-id="27df0-107">For information on how to generate MX Envelope schemas, please refer to the Form Generator Documentation.</span></span>  
  
4.  <span data-ttu-id="27df0-108">Agregue el esquema de sobre para el proyecto de SWIFT MX esquema.</span><span class="sxs-lookup"><span data-stu-id="27df0-108">Add the Envelope schema to the SWIFT MX Schema project.</span></span>  
  
5.  <span data-ttu-id="27df0-109">Abra el esquema de sobre en el editor de BizTalk y promocionar las propiedades "CorrelationToken" y "IsNewSubmission".</span><span class="sxs-lookup"><span data-stu-id="27df0-109">Open the Envelope schema in the BizTalk editor and promote “CorrelationToken” and “IsNewSubmission” properties.</span></span> <span data-ttu-id="27df0-110">Haga clic en los campos anteriores y haga clic en **promover -> promoción rápida** para promocionar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="27df0-110">Right-click the above fields and click **Promote -> Quick Promotion** to promote these properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27df0-111">Para obtener más información acerca de cómo promocionar las propiedades de un esquema, consulte la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="27df0-111">For more information on how to promote properties of a schema, please refer to the BizTalk Server documentation.</span></span>  
  
6.  <span data-ttu-id="27df0-112">Crear un archivo de clave (mediante Sn – k key.snk) y, a continuación, asigne al proyecto para crear un seguro con el nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="27df0-112">Create a key file (using Sn –k key.snk), and then assign it to the project to create a strong named assembly.</span></span>  
  
7.  <span data-ttu-id="27df0-113">Genere e implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="27df0-113">Build and then deploy the project.</span></span>
---
title: Administrar el secreto principal | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, managing
- managing [Master Secret server]
- SSO, Master Secret server
ms.assetid: f79e8f3f-c740-4ea1-9589-b42552fcd52d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2505fa6f5ec1abc04ded45e7701fd4e5212f889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-master-secret"></a><span data-ttu-id="f7455-102">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="f7455-102">Managing the Master Secret</span></span>
<span data-ttu-id="f7455-103">El secreto principal es la clave utilizada para cifrar toda la información almacenada en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="f7455-103">The master secret is the key used to encrypt all the information stored in the SSO database.</span></span> <span data-ttu-id="f7455-104">Si se produce un error en el servidor secreto principal y la clave se pierde, no podrá recuperar la información almacenada en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="f7455-104">If the master secret server fails and you lose the secret, you will not be able to retrieve the information stored in the SSO database.</span></span> <span data-ttu-id="f7455-105">Por lo tanto, es muy importante hacer una copia de seguridad del secreto principal inmediatamente después de generarlo.</span><span class="sxs-lookup"><span data-stu-id="f7455-105">Therefore, it is very important to back up the master secret as soon as you generate it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7455-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f7455-106">In This Section</span></span>  
  
-   [<span data-ttu-id="f7455-107">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="f7455-107">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="f7455-108">Cómo realizar copias de seguridad del secreto principal</span><span class="sxs-lookup"><span data-stu-id="f7455-108">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="f7455-109">Cómo restaurar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="f7455-109">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="f7455-110">Cómo mover el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="f7455-110">How to Move the Master Secret Server</span></span>](../core/how-to-move-the-master-secret-server.md)
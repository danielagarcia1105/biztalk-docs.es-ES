---
title: "Archivo de configuración XML para el adaptador de MQSeries | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, mqsconfigwiz
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], mqsconfigwiz
- mqsconfigwiz [MQSeries adapters]
ms.assetid: 5f19e55c-0f2c-46d7-bb5d-1eb147c296b3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0356c69b90f0dcfd5fc636b302a97b2de5674b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a><span data-ttu-id="b2647-102">Archivo de configuración XML para el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="b2647-102">XML Configuration File for the MQSeries Adapter</span></span>
<span data-ttu-id="b2647-103">Leer el archivo de configuración XML **mqsconfigwiz** contiene la misma información que un usuario especifica al usar la versión de Windows del asistente.</span><span class="sxs-lookup"><span data-stu-id="b2647-103">The XML configuration file read by **mqsconfigwiz** contains the same information a user enters when using the Windows version of the wizard.</span></span> <span data-ttu-id="b2647-104">Esta información incluye la identidad de aplicación, el Id. de usuario y la contraseña si es necesario, el nombre de función y una lista de usuarios que forman parte de la función.</span><span class="sxs-lookup"><span data-stu-id="b2647-104">This information includes the application identity and the user ID and password if required, the role name, and a list of users who are part of that role.</span></span>  
  
 <span data-ttu-id="b2647-105">A continuación se ofrece un ejemplo de este tipo de archivo:</span><span class="sxs-lookup"><span data-stu-id="b2647-105">An example of the file might appear as follows:</span></span>  
  
```  
<MQSeriesConfig>  
    <AppIdentity>thisuser</AppIdentity>  
    <userid>domain\username</userid>  
    <password>Bippity.Boppity</password>  
    <rolename>CreatorOwner</rolename>  
    <userlist>  
        <username>domain\user1</username>  
        <username>domain\user2</username>  
    </userlist>  
</MQSeriesConfig>  
```  
  
 <span data-ttu-id="b2647-106">Puede usar **thisuser**, **InteractiveUser**, **LocalService**, o **NetworkService** como valores para **AppIdentity** .</span><span class="sxs-lookup"><span data-stu-id="b2647-106">You can use **thisuser**, **InteractiveUser**, **LocalService**, or **NetworkService** as values for **AppIdentity**.</span></span> <span data-ttu-id="b2647-107">Use la **userid** y **contraseña** elementos sólo con **thisuser**.</span><span class="sxs-lookup"><span data-stu-id="b2647-107">Use the **userid** and **password** elements only with **thisuser**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2647-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2647-108">See Also</span></span>  
 [<span data-ttu-id="b2647-109">Configuración silenciosa del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="b2647-109">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)
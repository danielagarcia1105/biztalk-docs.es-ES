---
title: Solucionar problemas del adaptador de JD Edwards OneWorld | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba2dd62e1d4b6dc0af1845d3129e69dbe582226
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="5e2a1-102">Solucionar problemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="5e2a1-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="5e2a1-103">Este tema contiene información que le ayudará a identificar y resolver los problemas que pueden surgir al usar el adaptador de Microsoft BizTalk para JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="5e2a1-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a><span data-ttu-id="5e2a1-104">No se pueden utilizar comodines en las propiedades del puerto de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="5e2a1-104">Cannot use wildcards in send and receive port properties</span></span>  
 <span data-ttu-id="5e2a1-105">El adaptador para JD Edwards One World no admite el uso de comodines en los siguientes campos de propiedades:</span><span class="sxs-lookup"><span data-stu-id="5e2a1-105">Adapter for JD Edwards One World does not support using wildcards in the following property fields:</span></span>  
  
|<span data-ttu-id="5e2a1-106">Propiedad de puerto de envío</span><span class="sxs-lookup"><span data-stu-id="5e2a1-106">Send Port Property</span></span>|<span data-ttu-id="5e2a1-107">Propiedad de puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="5e2a1-107">Receive Port Property</span></span>|  
|------------------------|---------------------------|  
|<span data-ttu-id="5e2a1-108">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="5e2a1-108">Username</span></span>|<span data-ttu-id="5e2a1-109">Ruta de acceso del archivo del evento</span><span class="sxs-lookup"><span data-stu-id="5e2a1-109">Event File Path</span></span>|  
|<span data-ttu-id="5e2a1-110">Entorno JDE</span><span class="sxs-lookup"><span data-stu-id="5e2a1-110">JDE Environment</span></span>|<span data-ttu-id="5e2a1-111">Prefijo de nombre de destino del evento</span><span class="sxs-lookup"><span data-stu-id="5e2a1-111">Event Target Name prefix</span></span>|  
|<span data-ttu-id="5e2a1-112">Host</span><span class="sxs-lookup"><span data-stu-id="5e2a1-112">Host</span></span>||  
|<span data-ttu-id="5e2a1-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="5e2a1-113">Port</span></span>||  
|<span data-ttu-id="5e2a1-114">Java_Home</span><span class="sxs-lookup"><span data-stu-id="5e2a1-114">Java_Home</span></span>||  
|<span data-ttu-id="5e2a1-115">Archivos JAR de JDE</span><span class="sxs-lookup"><span data-stu-id="5e2a1-115">JDE JAR Files</span></span>||  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="5e2a1-116">Conectando a la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="5e2a1-116">Connecting to Oracle database</span></span>  
 <span data-ttu-id="5e2a1-117">Cuando se usa la base de datos de Oracle con JD Edwards debe modificarse el archivo jdeinterop.ini.</span><span class="sxs-lookup"><span data-stu-id="5e2a1-117">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="5e2a1-118">Mediante el Inicio de sesión único, la sección [JDBj-ORACLE] define la ubicación de tnsnames de Oracle; debe usarse el parámetro de base de datos; y el archivo SQLNET.ORA debe estar presente en el equipo de BizTalk Server (debe incluirse con el cliente Oracle).</span><span class="sxs-lookup"><span data-stu-id="5e2a1-118">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="5e2a1-119">Agregue lo siguiente al archivo jdeinterop.ini:</span><span class="sxs-lookup"><span data-stu-id="5e2a1-119">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="5e2a1-120">En [JDBj ORACLE], escriba:</span><span class="sxs-lookup"><span data-stu-id="5e2a1-120">Under [JDBj-ORACLE], type:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="5e2a1-121">En [JDBj-BOOTSTRAP DATA SOURCE], escriba:</span><span class="sxs-lookup"><span data-stu-id="5e2a1-121">Under [JDBj-BOOTSTRAP DATA SOURCE], type:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5e2a1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e2a1-122">See Also</span></span>  
 <span data-ttu-id="5e2a1-123">[Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   </span><span class="sxs-lookup"><span data-stu-id="5e2a1-123">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   </span></span>  
 [<span data-ttu-id="5e2a1-124">Solución de problemas de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="5e2a1-124">Troubleshoot JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)
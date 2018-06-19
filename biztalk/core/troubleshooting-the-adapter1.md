---
title: Solucionar problemas del adaptador de JD Edwards EnterpriseOne | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac716a7567930509ebfd310cdaf9874286b349c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013131"
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="c5fbd-102">Solucionar problemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="c5fbd-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="c5fbd-103">Este tema contiene información para ayudarle a identificar y resolver los problemas que pueda tener mientras usa el adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="c5fbd-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a><span data-ttu-id="c5fbd-104">No se pueden usar caracteres comodín en las propiedades de puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c5fbd-104">Cannot use wildcards in send port properties</span></span>  
 <span data-ttu-id="c5fbd-105">El adaptador de BizTalk para JD Edwards EnterpriseOne no admite el uso de caracteres comodín en los siguientes campos de propiedades de puertos de envío:</span><span class="sxs-lookup"><span data-stu-id="c5fbd-105">Adapter for JD Edwards Enterprise One does not support using wildcards in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="c5fbd-106">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="c5fbd-106">Username</span></span>  
  
-   <span data-ttu-id="c5fbd-107">Entorno JDE</span><span class="sxs-lookup"><span data-stu-id="c5fbd-107">JDE Environment</span></span>  
  
-   <span data-ttu-id="c5fbd-108">Host</span><span class="sxs-lookup"><span data-stu-id="c5fbd-108">Host</span></span>  
  
-   <span data-ttu-id="c5fbd-109">Puerto</span><span class="sxs-lookup"><span data-stu-id="c5fbd-109">Port</span></span>  
  
-   <span data-ttu-id="c5fbd-110">Java_Home</span><span class="sxs-lookup"><span data-stu-id="c5fbd-110">Java_Home</span></span>  
  
-   <span data-ttu-id="c5fbd-111">Archivos JAR de JDE</span><span class="sxs-lookup"><span data-stu-id="c5fbd-111">JDE JAR Files</span></span>  
  
-   <span data-ttu-id="c5fbd-112">Nombre del servidor de seguridad</span><span class="sxs-lookup"><span data-stu-id="c5fbd-112">Security Server Name</span></span>  
  
-   <span data-ttu-id="c5fbd-113">Conexión del nombre de servicio</span><span class="sxs-lookup"><span data-stu-id="c5fbd-113">Service Name Connect</span></span>  
  
-   <span data-ttu-id="c5fbd-114">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="c5fbd-114">Data Source Name</span></span>  
  
-   <span data-ttu-id="c5fbd-115">Propietario de la base de datos</span><span class="sxs-lookup"><span data-stu-id="c5fbd-115">Database Owner</span></span>  
  
-   <span data-ttu-id="c5fbd-116">Nombre del servidor de bases de datos</span><span class="sxs-lookup"><span data-stu-id="c5fbd-116">Database Server Name</span></span>  
  
-   <span data-ttu-id="c5fbd-117">Tipo de base de datos</span><span class="sxs-lookup"><span data-stu-id="c5fbd-117">Database Type</span></span>  
  
-   <span data-ttu-id="c5fbd-118">Nombre de la base de datos física</span><span class="sxs-lookup"><span data-stu-id="c5fbd-118">Physical Database Name</span></span>  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="c5fbd-119">Conectando a la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="c5fbd-119">Connecting to Oracle database</span></span>  
 <span data-ttu-id="c5fbd-120">Cuando se usa la base de datos de Oracle con JD Edwards debe modificarse el archivo jdeinterop.ini.</span><span class="sxs-lookup"><span data-stu-id="c5fbd-120">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="c5fbd-121">Mediante el Inicio de sesión único, la sección [JDBj-ORACLE] define la ubicación de tnsnames de Oracle; debe usarse el parámetro de base de datos; y el archivo SQLNET.ORA debe estar presente en el equipo de BizTalk Server (debe incluirse con el cliente Oracle).</span><span class="sxs-lookup"><span data-stu-id="c5fbd-121">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="c5fbd-122">Agregue lo siguiente al archivo jdeinterop.ini:</span><span class="sxs-lookup"><span data-stu-id="c5fbd-122">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="c5fbd-123">En [JDBj-ORACLE]:</span><span class="sxs-lookup"><span data-stu-id="c5fbd-123">Under [JDBj-ORACLE]:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="c5fbd-124">En [JDBj-BOOTSTRAP DATA SOURCE]:</span><span class="sxs-lookup"><span data-stu-id="c5fbd-124">Under [JDBj-BOOTSTRAP DATA SOURCE]:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5fbd-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5fbd-125">See Also</span></span>  
 <span data-ttu-id="c5fbd-126">[Agregar el adaptador y crear los artefactos](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="c5fbd-126">[Add the adapter, and create the artifacts](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="c5fbd-127">Solución de problemas de JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="c5fbd-127">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)
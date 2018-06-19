---
title: Error Messages1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a44049c43c499ac05a8a6f296d11add934267a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241620"
---
# <a name="error-messages"></a><span data-ttu-id="05008-102">mensajes de error</span><span class="sxs-lookup"><span data-stu-id="05008-102">Error Messages</span></span>
<span data-ttu-id="05008-103">En la tabla siguiente se describen los mensajes de error del sistema JD Edwards EnterpriseOne y se proporcionan posibles correcciones para ellos.</span><span class="sxs-lookup"><span data-stu-id="05008-103">The following table describes error messages in the JD Edwards EnterpriseOne system and provides possible corrections for them.</span></span>  
  
|<span data-ttu-id="05008-104">Id. de error</span><span class="sxs-lookup"><span data-stu-id="05008-104">Error ID</span></span>|<span data-ttu-id="05008-105">Posible causa/Descripción del error</span><span class="sxs-lookup"><span data-stu-id="05008-105">Possible Cause / Error Description</span></span>|<span data-ttu-id="05008-106">Posible corrección</span><span class="sxs-lookup"><span data-stu-id="05008-106">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="05008-107">E JDE0027</span><span class="sxs-lookup"><span data-stu-id="05008-107">E-JDE0027</span></span>|<span data-ttu-id="05008-108">Faltan archivos JAR de JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="05008-108">JD Edwards EnterpriseOne JAR files missing.</span></span> <span data-ttu-id="05008-109">No se puede adquirir el objeto de conexión JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="05008-109">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span>|<span data-ttu-id="05008-110">Compruebe sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="05008-110">Verify your credentials.</span></span> <span data-ttu-id="05008-111">Compruebe la configuración de CLASSPATH y las credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="05008-111">Verify your CLASSPATH settings and logon credentials.</span></span> <span data-ttu-id="05008-112">Consulte la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="05008-112">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="05008-113">I-JDE0043</span><span class="sxs-lookup"><span data-stu-id="05008-113">I-JDE0043</span></span>|<span data-ttu-id="05008-114">Servidor de aplicaciones, puerto, entorno, ruta de acceso para el archivo de configuración, usuario, contraseña incorrectos.</span><span class="sxs-lookup"><span data-stu-id="05008-114">Wrong App Server, Port, Environment, Path for Configuration File, User, Password.</span></span> <span data-ttu-id="05008-115">Error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="05008-115">Log in failed.</span></span>|<span data-ttu-id="05008-116">Verifique sus credenciales de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="05008-116">Verify your log in credentials.</span></span> <span data-ttu-id="05008-117">Consulte la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="05008-117">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="05008-118">I-JDE0048</span><span class="sxs-lookup"><span data-stu-id="05008-118">I-JDE0048</span></span>|<span data-ttu-id="05008-119">Si el archivo jdearglist.txt no existe o está vacío, aparece un mensaje informativo en el registro cuando se abre el adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="05008-119">If the jdearglist.txt file does not exist or is empty, an informational message appears in the log when Microsoft BizTalk Adapter for JD Edwards EnterpriseOne opens.</span></span>|<span data-ttu-id="05008-120">Actualice el archivo jdearglist.txt para especificar una lista de parámetros que se justifique automáticamente por la derecha y se rellene por la izquierda con espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="05008-120">Update the jdearglist.txt file to enter a list of parameters so that they are automatically right justified and padded on the left with blanks.</span></span> <span data-ttu-id="05008-121">Para obtener más información, consulte [control de valores de cadena](../core/handling-string-values2.md).</span><span class="sxs-lookup"><span data-stu-id="05008-121">For more information, see  [Handling String Values](../core/handling-string-values2.md).</span></span> <span data-ttu-id="05008-122">Cada vez que cambie jdearglist, debe volver a generar los esquemas para ese objeto de negocio.</span><span class="sxs-lookup"><span data-stu-id="05008-122">Every time you change the jdearglist, you must regenerate the schemas for that business object.</span></span>|  
|<span data-ttu-id="05008-123">E JDE0027</span><span class="sxs-lookup"><span data-stu-id="05008-123">E-JDE0027</span></span>|<span data-ttu-id="05008-124">No se puede adquirir el objeto de conexión JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="05008-124">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span> <span data-ttu-id="05008-125">Compruebe sus CLASSPATH y credenciales.</span><span class="sxs-lookup"><span data-stu-id="05008-125">Please check your CLASSPATH and credentials.</span></span>|<span data-ttu-id="05008-126">Compruebe la ubicación del jdeinterop.ini.</span><span class="sxs-lookup"><span data-stu-id="05008-126">Verify the location of jdeinterop.ini.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05008-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="05008-127">See Also</span></span>  
 <span data-ttu-id="05008-128">[Solución de problemas de JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="05008-128">[Troubleshooting JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="05008-129">Referencia técnica</span><span class="sxs-lookup"><span data-stu-id="05008-129">Technical Reference</span></span>](../core/technical-reference6.md)
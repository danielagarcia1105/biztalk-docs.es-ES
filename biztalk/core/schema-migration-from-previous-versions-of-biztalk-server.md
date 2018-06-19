---
title: Migración de esquema desde versiones anteriores de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc86401-2002-40b8-a919-2c00cf42b557
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1666e7cc8459fd4418e0ba0963caf5b654975805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269628"
---
# <a name="schema-migration-from-previous-versions-of-biztalk-server"></a><span data-ttu-id="89228-102">Migración de esquemas de versiones anteriores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="89228-102">Schema Migration from Previous Versions of BizTalk Server</span></span>
<span data-ttu-id="89228-103">Esta versión de BizTalk Server usa el lenguaje de definición de esquemas XML (XSD) para representar los esquemas de mensajes, mientras que las versiones anteriores utilizaban la sintaxis de datos reducidos XML (XDR) para representarlos.</span><span class="sxs-lookup"><span data-stu-id="89228-103">This version of BizTalk Server uses XML Schema definition (XSD) language to represent message schemas, while previous versions used the XML-Data Reduced (XDR) syntax to represent message schemas.</span></span> <span data-ttu-id="89228-104">Si migra desde una versión anterior de BizTalk Server, debe convertir los esquemas para que utilicen XSD en lugar de XDR.</span><span class="sxs-lookup"><span data-stu-id="89228-104">If you are migrating from a previous version of BizTalk Server, you must convert your schemas to use XSD rather than XDR.</span></span>  
  
 <span data-ttu-id="89228-105">Debe realizar las siguientes tareas para convertir un esquema de BizTalk de la sintaxis XDR a la sintaxis XSD:</span><span class="sxs-lookup"><span data-stu-id="89228-105">You need to perform the following tasks to convert a BizTalk schema from XDR syntax to XSD syntax:</span></span>  
  
-   <span data-ttu-id="89228-106">Cambie la extensión del archivo de esquema de .xdr a .xsd.</span><span class="sxs-lookup"><span data-stu-id="89228-106">Change the extension of the schema file from.xdr to.xsd.</span></span>  
  
-   <span data-ttu-id="89228-107">Agregue el esquema cuyo nombre ha cambiado al proyecto de BizTalk correspondiente.</span><span class="sxs-lookup"><span data-stu-id="89228-107">Add the renamed schema to the appropriate BizTalk project.</span></span>  
  
-   <span data-ttu-id="89228-108">Convierta el esquema cuyo nombre ha cambiado de XDR a XSD. Para ello, abra el esquema en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="89228-108">Convert the renamed schema from XDR to XSD by opening the schema in BizTalk Editor.</span></span>  
  
-   <span data-ttu-id="89228-109">Guarde el esquema para que la conversión se almacene de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="89228-109">Make the conversion permanent by saving the schema.</span></span>  
  
 <span data-ttu-id="89228-110">Para obtener información detallada sobre cómo realizar estos pasos, consulte [cómo migrar esquemas XDR en esquemas XSD](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="89228-110">For detailed information about how to perform these steps, see [How to Migrate XDR Schemas to XSD Schemas](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89228-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="89228-111">See Also</span></span>  
 <span data-ttu-id="89228-112">[Acerca de los esquemas](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="89228-112">[About Schemas](../core/about-schemas.md) </span></span>  
 <span data-ttu-id="89228-113">[Cómo migrar esquemas XDR en esquemas XSD](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="89228-113">[How to Migrate XDR Schemas to XSD Schemas](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md) </span></span>  
 [<span data-ttu-id="89228-114">Migrar registros de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="89228-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)
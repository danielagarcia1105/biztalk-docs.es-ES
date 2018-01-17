---
title: "Cómo migrar esquemas XDR a esquemas XSD | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84bbc42297a10c7d42adb8d778ba19b3b392742c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a><span data-ttu-id="204ba-102">Cómo migrar esquemas XDR a esquemas XSD</span><span class="sxs-lookup"><span data-stu-id="204ba-102">How to Migrate XDR Schemas to XSD Schemas</span></span>
<span data-ttu-id="204ba-103">Si va a migrar esquemas de una versión anterior de BizTalk Server, deberá convertir los esquemas de datos reducidos XML (XDR) a esquemas de lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="204ba-103">If you are migrating schemas from a previous version of BizTalk Server, you will need to convert your XML-Data Reduced (XDR) schemas into XML Schema definition (XSD) language schemas.</span></span> <span data-ttu-id="204ba-104">En este tema se describe los pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="204ba-104">This topic describes the necessary steps.</span></span>  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a><span data-ttu-id="204ba-105">Para generar un esquema XSD a partir de un esquema XDR</span><span class="sxs-lookup"><span data-stu-id="204ba-105">To generate an XSD schema from an XDR schema</span></span>  
  
1.  <span data-ttu-id="204ba-106">En **el Explorador de soluciones**, haga clic en el proyecto de BizTalk correspondiente, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="204ba-106">In **Solution Explorer**, right-click the relevant BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="204ba-107">En el **agregar elementos generados - \< *BizTalk ProjectName* \>**  cuadro de diálogo, en la **plantillas** sección, haga clic en **generar Esquemas**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="204ba-107">In the **Add Generated Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="204ba-108">En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista, seleccione **esquema XDR**.</span><span class="sxs-lookup"><span data-stu-id="204ba-108">In the **Generate Schemas** dialog box, in the **Document type** list, select **XDR Schema**.</span></span>  
  
4.  <span data-ttu-id="204ba-109">Haga clic en **examinar**, busque el archivo de esquema XDR que desea migrar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="204ba-109">Click **Browse**, locate the XDR schema file you want to migrate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="204ba-110">A partir del archivo de esquema XDR especificado se crea un esquema nuevo con el mismo nombre que dicho archivo y la extensión .xsd y, a continuación, se abre en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="204ba-110">A new schema is generated from the specified XDR schema file, using the same name as that file with the .xsd extension, and then opened in BizTalk Editor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="204ba-111">Evite el uso de palabras reservadas de C# y nombres de tipos y de espacios de nombres de .NET Framework (como System) en los nombres de los nodos raíz de esquema o en los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="204ba-111">Avoid using C# reserved words and .NET Framework type and namespace names (such as System) as schema root node names or as file names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="204ba-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="204ba-112">See Also</span></span>  
 <span data-ttu-id="204ba-113">[Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="204ba-113">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="204ba-114">Migración de registros de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="204ba-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)
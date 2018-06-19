---
title: Propiedades del acuerdo de la importación de un archivo XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc0bd397e49dcad670bb73e9dff9c164b9d0997a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006853"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="072aa-102">Importación de propiedades de acuerdo de un archivo XML</span><span class="sxs-lookup"><span data-stu-id="072aa-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="072aa-103">Esta sección proporciona instrucciones de cómo importar propiedades de acuerdo desde un archivo de plantilla XML.</span><span class="sxs-lookup"><span data-stu-id="072aa-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="072aa-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="072aa-104">Prerequisites</span></span>  
 <span data-ttu-id="072aa-105">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="072aa-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="072aa-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="072aa-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
-   <span data-ttu-id="072aa-107">Debe haber exportado un acuerdo a un archivo de plantilla XML, como se describe en [propiedades del acuerdo de exportar a un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="072aa-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="072aa-108">Para importar propiedades de acuerdo desde un archivo XML</span><span class="sxs-lookup"><span data-stu-id="072aa-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="072aa-109">En la consola de administración de BizTalk Server, haga clic en el **partes** nodo bajo el **administración de BizTalk Server** y **grupo de BizTalk** nodos.</span><span class="sxs-lookup"><span data-stu-id="072aa-109">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="072aa-110">En el **entidades y perfiles empresariales** página, cree un acuerdo como se describe en [General configuración (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="072aa-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="072aa-111">En el **propiedades del acuerdo de** cuadro de diálogo, haga clic en **cargar desde plantilla**.</span><span class="sxs-lookup"><span data-stu-id="072aa-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="072aa-112">El **cargar desde plantilla** botón se habilita solo después de seleccionar un protocolo para el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="072aa-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="072aa-113">Al especificar el protocolo también declara implícitamente que únicamente importa un acuerdo para el mismo protocolo de codificación.</span><span class="sxs-lookup"><span data-stu-id="072aa-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="072aa-114">En el **abiertos** cuadro de diálogo, vaya a la ubicación del archivo de plantilla XML, seleccione el archivo y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="072aa-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="072aa-115">En el **crear plantilla** cuadro, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="072aa-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072aa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="072aa-116">See Also</span></span>  
 <span data-ttu-id="072aa-117">[Volver a usar propiedades de otro acuerdo](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="072aa-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="072aa-118">Exportación de propiedades del acuerdo a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="072aa-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)
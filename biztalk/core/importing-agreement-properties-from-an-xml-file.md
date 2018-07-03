---
title: Importación desde un archivo XML de las propiedades del acuerdo | Microsoft Docs
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
ms.openlocfilehash: cafd590f4f5936c1d12614e7a2021bc5427d49d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969149"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="6005a-102">Importación de propiedades de acuerdo de un archivo XML</span><span class="sxs-lookup"><span data-stu-id="6005a-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="6005a-103">Esta sección proporciona instrucciones de cómo importar propiedades de acuerdo desde un archivo de plantilla XML.</span><span class="sxs-lookup"><span data-stu-id="6005a-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6005a-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6005a-104">Prerequisites</span></span>  
 <span data-ttu-id="6005a-105">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="6005a-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="6005a-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6005a-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="6005a-107">Debe haber exportado un acuerdo a un archivo de plantilla XML, como se describe en [exportar las propiedades del acuerdo en un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="6005a-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="6005a-108">Para importar propiedades de acuerdo desde un archivo XML</span><span class="sxs-lookup"><span data-stu-id="6005a-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="6005a-109">En la consola de administración de BizTalk Server, haga clic en el **partes** nodo bajo el **administración de BizTalk Server** y **grupo de BizTalk** nodos.</span><span class="sxs-lookup"><span data-stu-id="6005a-109">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="6005a-110">En el **entidades y perfiles empresariales** página, cree un acuerdo como se describe en [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="6005a-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="6005a-111">En el **las propiedades del acuerdo** cuadro de diálogo, haga clic en **cargar desde plantilla**.</span><span class="sxs-lookup"><span data-stu-id="6005a-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6005a-112">El **cargar desde plantilla** botón está habilitado solo después de seleccionar un protocolo para el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="6005a-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="6005a-113">Al especificar el protocolo también declara implícitamente que únicamente importa un acuerdo para el mismo protocolo de codificación.</span><span class="sxs-lookup"><span data-stu-id="6005a-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="6005a-114">En el **abierto** cuadro de diálogo, vaya a la ubicación del archivo de plantilla XML, seleccione el archivo y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="6005a-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="6005a-115">En el **crear plantilla** cuadro, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6005a-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6005a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6005a-116">See Also</span></span>  
 <span data-ttu-id="6005a-117">[Volver a usar propiedades de otro acuerdo](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="6005a-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="6005a-118">Exportación de propiedades del acuerdo a un archivo XML</span><span class="sxs-lookup"><span data-stu-id="6005a-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)
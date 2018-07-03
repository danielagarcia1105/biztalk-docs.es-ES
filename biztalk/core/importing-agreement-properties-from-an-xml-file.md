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
# <a name="importing-agreement-properties-from-an-xml-file"></a>Importación de propiedades de acuerdo de un archivo XML
Esta sección proporciona instrucciones de cómo importar propiedades de acuerdo desde un archivo de plantilla XML.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
- Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Debe haber exportado un acuerdo a un archivo de plantilla XML, como se describe en [exportar las propiedades del acuerdo en un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md).  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a>Para importar propiedades de acuerdo desde un archivo XML  
  
1.  En la consola de administración de BizTalk Server, haga clic en el **partes** nodo bajo el **administración de BizTalk Server** y **grupo de BizTalk** nodos. En el **entidades y perfiles empresariales** página, cree un acuerdo como se describe en [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md).  
  
2.  En el **las propiedades del acuerdo** cuadro de diálogo, haga clic en **cargar desde plantilla**.  
  
    > [!NOTE]
    >  El **cargar desde plantilla** botón está habilitado solo después de seleccionar un protocolo para el acuerdo. Al especificar el protocolo también declara implícitamente que únicamente importa un acuerdo para el mismo protocolo de codificación.  
  
3.  En el **abierto** cuadro de diálogo, vaya a la ubicación del archivo de plantilla XML, seleccione el archivo y, a continuación, haga clic en **abierto**.  
  
4.  En el **crear plantilla** cuadro, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Volver a usar propiedades de otro acuerdo](../core/reusing-properties-from-another-agreement.md)   
 [Exportación de propiedades del acuerdo a un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md)
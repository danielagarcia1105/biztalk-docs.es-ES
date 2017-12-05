---
title: "Propiedades del acuerdo de la importación de un archivo XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc0bd397e49dcad670bb73e9dff9c164b9d0997a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="importing-agreement-properties-from-an-xml-file"></a>Importación de propiedades de acuerdo de un archivo XML
Esta sección proporciona instrucciones de cómo importar propiedades de acuerdo desde un archivo de plantilla XML.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Debe haber exportado un acuerdo a un archivo de plantilla XML, como se describe en [propiedades del acuerdo de exportar a un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md).  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a>Para importar propiedades de acuerdo desde un archivo XML  
  
1.  En la consola de administración de BizTalk Server, haga clic en el **partes** nodo bajo el **administración de BizTalk Server** y **grupo de BizTalk** nodos. En el **entidades y perfiles empresariales** página, cree un acuerdo como se describe en [General configuración (X12)](../core/configuring-general-settings-x12.md).  
  
2.  En el **propiedades del acuerdo de** cuadro de diálogo, haga clic en **cargar desde plantilla**.  
  
    > [!NOTE]
    >  El **cargar desde plantilla** botón se habilita solo después de seleccionar un protocolo para el acuerdo. Al especificar el protocolo también declara implícitamente que únicamente importa un acuerdo para el mismo protocolo de codificación.  
  
3.  En el **abiertos** cuadro de diálogo, vaya a la ubicación del archivo de plantilla XML, seleccione el archivo y, a continuación, haga clic en **abiertos**.  
  
4.  En el **crear plantilla** cuadro, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Volver a usar propiedades de otro acuerdo](../core/reusing-properties-from-another-agreement.md)   
 [Exportación de propiedades del acuerdo a un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md)
---
title: Validar una asignación (EDI) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6cfe1394d82f4fedb57aacb40bad27c95de2a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993341"
---
# <a name="validating-a-map-edi"></a>Validar una asignación (EDI)
Las asignaciones pueden validarse en tiempo de diseño. Para ello, usa las extensiones de herramientas de XML a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] entorno. Esta operación genera un archivo que contiene el XSLT subyacente de la asignación y un archivo que contiene objetos de extensión.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-validate-a-map"></a>Para validar una asignación  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto. En el proyecto del Explorador de soluciones, incluya la asignación que desea validar, así como sus esquemas de mensaje de entrada y salida.  
  
   > [!NOTE]
   >  Los esquemas de mensaje se encuentran en la subcarpeta correspondiente de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI. Para obtener más información acerca de cómo instalar los archivos de esquema, vea [cómo instalar archivos de esquema EDI](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).  
   > 
   > [!NOTE]
   >  No tiene que generar el proyecto para validar una asignación.  
  
2. Haga clic en el mapa en el Explorador de soluciones y, a continuación, haga clic en **validar asignación**.  
  
3. Compruebe que existe un mensaje en la ventana Resultados que le indica que la operación se ha realizado correctamente.  
  
4. Tenga en cuenta las advertencias que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha publicado en el **salida** ventana.  
  
5. En el **salida** ventana, tenga en cuenta el nombre y ruta de acceso de la salida XSLT. Este archivo XSL recibirá el mismo nombre que el archivo de la asignación, pero con la extensión XLS. Para ver el archivo XLS en el Editor de BizTalk, presione CTRL y haga clic en el vínculo.  
  
6. En el **salida** ventana, tenga en cuenta el nombre y ruta de acceso del objeto de extensión XML. Para ver el archivo XLS en el Editor de BizTalk, presione CTRL y haga clic en el vínculo.  
  
## <a name="see-also"></a>Vea también  
 [Uso de herramientas de XML en tiempo de diseño](../core/using-design-time-xml-tools.md)
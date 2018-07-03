---
title: Validar un esquema (EDI) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6175460-2dcf-4fef-b770-02f0a058bf93
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12f54b77420a9e03e701c5e154bba681b46c166c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997517"
---
# <a name="validating-a-schema-edi"></a>Validar un esquema (EDI)
Un esquema EDI se puede validar en tiempo de diseño. Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. La operación de validación de esquema valida el esquema según reglas EDI. No tiene que designar una instancia de mensaje de entrada para validar un esquema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-validate-a-schema"></a>Para validar un esquema  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto. En el proyecto del Explorador de soluciones, agregue el esquema de mensaje que desee validar.  
  
   > [!NOTE]
   >  Los esquemas de mensaje se encuentran en la subcarpeta correspondiente de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI. Para obtener información acerca de cómo instalar los archivos de esquema, vea [cómo instalar archivos de esquema EDI](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).  
   > 
   > [!NOTE]
   >  No tiene que generar el proyecto para validar un esquema.  
  
2. Haga clic en el esquema en el Explorador de soluciones y, a continuación, haga clic en **Validar esquema**.  
  
3. Compruebe que existe un mensaje en la ventana Resultados que le indica que la operación se ha realizado correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Uso de herramientas de XML en tiempo de diseño](../core/using-design-time-xml-tools.md)
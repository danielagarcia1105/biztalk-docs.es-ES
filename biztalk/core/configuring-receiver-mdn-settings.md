---
title: Configuración de MDN de receptor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafe17a0ad357b840b31d8a10c67e1ae3cc1e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233380"
---
# <a name="configuring-receiver-mdn-settings"></a>Configuración de MDN de receptor
Como parte de la configuración de MDN de receptor, se pueden especificar las propiedades que rigen la generación de MDN, en función de la cabecera del mensaje AS2.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-receiver-mdn-settings"></a>Para configurar el MDN de receptor  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **configuración de MDN de receptor**.  
  
3.  Si no activó la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad en el **validaciones** página, se puede elegir que la entidad que envía el MDN, firmar el MDN si generación del MDN está habilitada por la **Disposition-Notification-to** encabezado de AS2, pero la **Disposition-Notification-Options** encabezado no habilitar la firma. Esto puede ocurrir si **Disposition-Notification-Options** no está establecida o está establecido en opcional. Puede hacerlo haciendo clic en **firmar el MDN solicitado si el encabezado Disposition-Notification-Option no está predefinida o si el encabezado Signed-Receipt-Protocol está establecido en opcional**.  
  
4.  Puede escribir un texto en el **texto de MDN** campo para que la entidad que envía el MDN lo agregue al mensaje MDN (en el campo Content-Description). Esta configuración es aplicable independientemente de si el MDN se ha generado en función de los encabezados de AS2 o de las propiedades del acuerdo.  
  
5.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del Host Local (AS2)](../core/configuring-local-host-settings-as2.md)
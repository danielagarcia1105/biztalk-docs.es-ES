---
title: Configuración de certificados de firma (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a52962976c2db62de902906f53f5c270e2c7c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233268"
---
# <a name="configuring-signature-certificates-as2"></a>Configuración de certificados de firma (AS2)
Como parte de la configuración de esta página, puede especificar los certificados que se deben usar para firmar todos los mensajes salientes y el MDN que se resuelve en este acuerdo. La configuración de esta página invalida la configuración de certificado proporcionada en las propiedades del grupo de BizTalk. Para obtener más información sobre cómo se usan certificados, consulte [configurar certificados para AS2](../core/configuring-certificates-for-as2.md).  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-agreement-level-signature-certificate"></a>Para configurar certificados de firma de nivel de acuerdo  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, haga clic en **certificados de firma de**.  
  
3.  Seleccione el **certificado de firma de grupo de invalidación** casilla de verificación para usar el certificado proporcionado en esta página para firmar mensajes AS2 salientes y MDN.  
  
4.  Haga clic en **examinar** para mostrar la **Seleccionar certificado** cuadro de diálogo, donde podrá seleccionar el certificado de firma que se aplicará a los mensajes transmitidos por esta entidad.  
  
5.  El **nombre común** cuadro de texto muestra una descripción del certificado seleccionado.  
  
6.  El **huella digital** cuadro de texto muestra la huella digital del certificado. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.  
  
7.  Haga clic en **quitar certificado** para quitar el certificado seleccionado.  
  
8.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades del acuerdo de AS2](../core/configuring-as2-agreement-properties.md)
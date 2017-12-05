---
title: Crear o editar un socio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- trading partners
- modifying, trading partners
- trading partners, creating
- trading partners, modifying
- trading partners, about trading partners
ms.assetid: 63809035-65a5-472d-b2e5-359c8e9d9d8c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2236a7a438d96e51a606470e1607afb1b54aa7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="creating-or-editing-a-partner"></a>Crear o editar un socio
En este tema se describe cómo crear o editar a un socio. La configuración del socio comercial describe y clasifica al socio comercial, establece sin repudio del período de origen, configura los certificados para el socio comercial y proporciona información de contacto.  
  
 Cuando se crea un asociado, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] crea dos puertos de envío que va a usar ese asociado, uno asincrónica y otra sincrónica. Estos se denominan puertos de envío \< *nombre del asociado de*\>. Puerto de envío asincrónico y \< *nombre del asociado de*\>. Puerto de envío de sincronización. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]automáticamente se da de alta e inicia estos basados en el acuerdo de socio comercial de puertos de envío. Puede ver estos puertos en la consola de administración de BizTalk.  
  
 Configuración de socios comerciales es como se muestra en la siguiente tabla, organizada por pestaña. Para obtener instrucciones acerca de cómo crear y editar a un socio, consulte los procedimientos después de la tabla.  
  
|Pestaña|Configuración|Uso|  
|---------|-------------|-----------|  
|**General**|**Nombre**|El nombre para el socio comercial.<br /><br /> Campo obligatorio.<br /><br /> Longitud máxima: 255|  
|**General**|**GBI**|El identificador Global de negocio para el socio comercial. Esto debe ser nueve dígitos y debe corresponderse con el número DUNS.<br /><br /> Campo obligatorio.|  
|**General**|**Description**|Una descripción que identifica al socio comercial.|  
|**General**|**Mantener hasta**|La fecha en la que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviará un mensaje a la tabla MessagesFromLOB. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no se entregará este mensaje hasta que el **reserven hasta** fecha. Socios comerciales deben acordar esta fecha, en función de si el socio receptor estará listo para recibir el mensaje. Esta configuración puede resultar útil si un asociado no estará disponible para procesar los mensajes, por ejemplo, durante un día no laborable.<br /><br /> El valor predeterminado es la fecha actual.|  
|**General**|**Clasificación de socio comercial**|El tipo de la organización del asociado.<br /><br /> Puede ser **portadora** (valor predeterminado), **distribuidor**, **usuario final**, **gobierno del usuario final**, **Financier**, **Fabricante**, **minorista**, o **comprador**.<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]incluye el valor de este campo en el encabezado de servicio.<br /><br /> Puede especificar otro valor para la clasificación de socio comercial en el encabezado de servicio de un mensaje, reemplaza esta propiedad, escribiendo una propiedad personalizada PPCC en la ficha de propiedades personalizadas del acuerdo. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).|  
|**General**|**Sin repudio de origen**|El número de días [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] contendrá el formato de un mensaje en la base de datos MessageStorageIn o MessageStorageOut sin repudio (demostrar legalmente que ha recibido). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]se marca esta fecha en cada mensaje entrante o saliente.<br /><br /> El valor predeterminado es 2485 días.<br /><br /> Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no eliminará un mensaje desde la base de datos tras la expiración del período. Si desea eliminar estos mensajes, desarrolle una secuencia de comandos SQL para eliminar los mensajes antiguos en función de esta marca de fecha y hora.|  
|**General**<br /><br /> (**Certificados de clave pública** área)|**Firma**|La clave pública de certificado que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] va a utilizar para comprobar la firma del asociado en un mensaje entrante. Este certificado debe almacenarse en el almacén de certificados otras personas en el nodo certificados (equipo Local) en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.<br /><br /> El valor predeterminado es \<ninguno\>.|  
|**General**<br /><br /> (**Certificados de clave pública** área)|**Cifrado**|El cifrado de clave pública de certificado que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] va a usar para cifrar los mensajes salientes a un socio comercial. Este certificado debe almacenarse en el almacén de certificados otras personas en el nodo certificados (equipo Local) en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.<br /><br /> El valor predeterminado es \<ninguno\>.|  
|**Póngase en contacto con propiedades**|**Nombre de contacto**|El nombre del contacto en el socio comercial.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Dirección de correo electrónico**|La dirección de correo electrónico del contacto en el socio comercial.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Número de teléfono**|El número de teléfono del contacto en el socio comercial.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Número de fax**|El número de fax del contacto en el socio comercial.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Código de la cadena de suministro**|El código de la cadena de fuente de alimentación para el socio comercial. Por ejemplo, "Información de la tecnología" o "Componentes electrónicos".<br /><br /> Campo obligatorio.|  
  
### <a name="to-create-a-partner"></a>Para crear un socio  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic en **socios**, seleccione **New**y, a continuación, haga clic en **asociado**.  
  
4.  En el **nuevas propiedades de socio comercial** cuadro de diálogo la **General** y **póngase en contacto con propiedades** pestañas, con valores de tipo para la configuración. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-edit-a-partner"></a>Para editar un socio  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en **socios**.  
  
3.  Haga clic en el socio que desea editar y, a continuación, haga clic en **propiedades**.  
  
4.  En el  **\<**  *asociado*  **\>**  cuadro de diálogo de propiedades de la **General** y  **Póngase en contacto con propiedades** pestañas, cambiar la configuración según sea necesario. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Administración de la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)
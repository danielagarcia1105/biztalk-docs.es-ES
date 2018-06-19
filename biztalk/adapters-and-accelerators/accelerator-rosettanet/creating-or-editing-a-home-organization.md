---
title: Creación o edición de la organización principal | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- home organizations, about home organizations
- home organizations, modifying
- creating, home organizations
- modifying, home organizations
- home organizations
- home organizations, creating
ms.assetid: b54afb84-2f16-4516-8701-b03301476362
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1027e30e847c4f35b9270083ad56074967072467
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964962"
---
# <a name="creating-or-editing-a-home-organization"></a>Creación o edición de la organización principal
En este tema se describe cómo crear o editar la organización principal. La configuración de la organización principal describe y clasifica la organización, establece sin repudio del período de origen y proporcione información de contacto.  
  
 La configuración de la organización principal no incluye la firma y certificados de descifrado, como la configuración del socio comercial no. Configurar el certificado de firma para el grupo de BizTalk en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Configure el certificado de descifrado de los Hosts de BizTalk (BizTalkServerApplication y BizTalkIsolatedHost) en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Puede crear dos organizaciones internas dentro de una única compañía o implementación. Un ejemplo de esto podría ser una instancia en la que desea crear el tratamiento de prioridad de los mensajes, en qué mensajes se enlazan para una organización sería una mayor prioridad que los mensajes enlazados por otra cosa. Al crear varias organizaciones internas, debe proporcionar cada organización principal con un número DUNS independiente para identificar de forma única. El número DUNS es lo que define la conexión de RosettaNet.  
  
 La configuración en la descripción de la organización principal es como se muestra en la siguiente tabla, organizada por pestaña. Para obtener instrucciones sobre cómo crear y editar la organización principal, consulte los procedimientos después de la tabla.  
  
|Pestaña|Configuración|Uso|  
|---------|-------------|-----------|  
|**General**|**Nombre**|El nombre de la organización propia.<br /><br /> Campo obligatorio.<br /><br /> Longitud máxima: 255|  
|**General**|**GBI**|El identificador Global de negocio de la organización propia. Esto debe ser nueve dígitos de longitud y debe corresponderse con el número DUNS.<br /><br /> Campo obligatorio.|  
|**General**|**Description**|Una descripción que le ayude a identificar la organización principal.|  
|**General**|**Clasificación de la organización principal**|La naturaleza de la organización.<br /><br /> Puede ser **usuario final**, **gobierno del usuario final**, **Financier**, **fabricante**, **minorista**,  **Comprador**, **flete reenviador**, o **Marketplace**.<br /><br /> Puede especificar otro valor para la clasificación de la organización principal en el encabezado de servicio de un mensaje, reemplaza esta propiedad, escribiendo una propiedad personalizada de HPCC en la ficha de propiedades personalizadas del acuerdo. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).|  
|**Póngase en contacto con propiedades**|**Nombre de contacto**|El nombre del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Dirección de correo electrónico**|La dirección de correo electrónico del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Número de teléfono**|El número de teléfono del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Número de fax**|El número de fax del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Código de la cadena de suministro**|El código de cadena de suministro de la organización principal.<br /><br /> Campo obligatorio.|  
  
### <a name="to-create-a-home-organization-definition"></a>Para crear una definición de la organización principal  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic en **organizaciones principales**, seleccione **New**y, a continuación, haga clic en **organización principal**.  
  
4.  En el cuadro de diálogo nuevas propiedades de organización de inicio, en el **General** y **póngase en contacto con propiedades** pestañas, escriba los valores de configuración. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-edit-a-home-organization"></a>Para editar la organización principal  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic en **inicio organizaciones**.  
  
4.  Haga clic en la organización principal que desea editar y, a continuación, haga clic en **propiedades**.  
  
5.  En el  *\<principal organización\>*  cuadro de diálogo de propiedades el **General** y **póngase en contacto con propiedades** pestañas, cambie la configuración según sea necesario. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Administración de la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)
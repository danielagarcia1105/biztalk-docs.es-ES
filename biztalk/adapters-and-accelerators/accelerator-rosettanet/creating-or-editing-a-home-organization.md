---
title: Creación o edición de la organización principal | Microsoft Docs
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
ms.openlocfilehash: 4a1c9d43ba83e6b5b861662f268aeac561e3d377
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998701"
---
# <a name="creating-or-editing-a-home-organization"></a>Creación o edición de la organización principal
Este tema describe cómo crear o editar la organización principal. La configuración de la organización principal describe y clasifica de la organización, Establece el rechazo del período de origen y proporciona información de contacto.  
  
 La configuración de la organización principal no incluye la firma y certificados de descifrado, como la configuración del socio comercial hace. Configurar el certificado de firma para el grupo de BizTalk en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Configurar el certificado de descifrado para los Hosts de BizTalk (BizTalkServerApplication y BizTalkIsolatedHost) en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Puede crear dos organizaciones principales dentro de una sola empresa o la implementación. Un ejemplo de esto podría ser una instancia en el que desea crear el tratamiento de prioridad de los mensajes, en los mensajes que se enlaza para una organización sería una mayor prioridad que los mensajes destinados a otra. Al crear varias organizaciones principales, debe proporcionar cada organización principal con un número DUNS independiente para identificar de forma única. El número DUNS es lo que define la conexión de RosettaNet.  
  
 La configuración en la descripción de la organización principal es como se muestra en la siguiente tabla, organizada por pestaña. Para obtener instrucciones sobre cómo crear y editar la organización principal, consulte los procedimientos después de la tabla.  
  
|Pestaña|Configuración|Uso|  
|---------|-------------|-----------|  
|**General**|**Nombre**|El nombre de la organización propia.<br /><br /> Campo obligatorio.<br /><br /> Longitud máxima: 255|  
|**General**|**GBI**|El identificador de empresa Global de la organización principal. Esto debe ser de nueve dígitos de longitud y debe corresponder al número DUNS.<br /><br /> Campo obligatorio.|  
|**General**|**Descripción**|Una descripción que le ayudarán a identificar la organización principal.|  
|**General**|**Clasificación de la organización principal**|La naturaleza de la organización.<br /><br /> Puede ser **usuario final**, **gobierno del usuario final**, **Financier**, **fabricante**, **minorista**,  **Comprador**, **carta de porte de reenviador**, o **Marketplace**.<br /><br /> Puede especificar otro valor para la clasificación de la organización principal en el encabezado de servicio de un mensaje, reemplaza esta propiedad, escribiendo una propiedad personalizada HPCC en la ficha de propiedades personalizadas del acuerdo. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).|  
|**Póngase en contacto con propiedades**|**Nombre de contacto**|El nombre del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Dirección de correo electrónico**|La dirección de correo electrónico del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Número de teléfono**|El número de teléfono del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Número de fax**|El número de fax del contacto en la organización principal.<br /><br /> Campo obligatorio.|  
|**Póngase en contacto con propiedades**|**Código de la cadena de suministro**|El código de la cadena de suministro de la organización propia.<br /><br /> Campo obligatorio.|  
  
### <a name="to-create-a-home-organization-definition"></a>Para crear una definición de la organización principal  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
2. En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3. Haga clic en **organizaciones principales**, apunte a **New**y, a continuación, haga clic en **organización principal**.  
  
4. En el cuadro de diálogo nuevas propiedades de organización de inicio, en el **General** y **propiedades del contacto** pestañas, escriba los valores de configuración. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
5. Haga clic en **Aceptar**.  
  
### <a name="to-edit-a-home-organization"></a>Para editar la organización principal  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
2. En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3. Haga clic en **Home organizaciones**.  
  
4. Haga clic en la organización principal que desea editar y, a continuación, haga clic en **propiedades**.  
  
5. En el *\<home organización\>* cuadro de diálogo de propiedades el **General** y **propiedades del contacto** fichas, cambie la configuración según sea necesario. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
6. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Administración de la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)
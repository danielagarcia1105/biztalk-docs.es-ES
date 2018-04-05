---
title: Administrar perfiles de negocio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.businessprofile
ms.assetid: cf98c5a4-71bb-440b-8172-717ed0eb8373
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 434979376e679f1098557dc5b55f50e599ed21cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-business-profiles"></a>Administración de perfiles de negocio
Un perfil de negocio representa las divisiones de negocio dentro de una organización. Al igual que una organización puede tener distintas divisiones, una entidad puede tener varios [perfiles de negocio](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf). 
  
Un perfil de negocio representa una división de negocio de una organización. Al igual que una organización puede tener muchas divisiones (contabilidad, compras, envíos, etc.), una entidad puede tener muchos perfiles de negocio, cada uno de los cuales representa una división de negocio de una organización. Las propiedades del perfil de negocio contienen la información siguiente:  
  
-   Información general como el nombre del perfil de negocio  
  
-   Identidades únicas que pueden asociarse a un perfil de negocio  
  
-   Configuración de codificación (mensajes X12 y EDIFACT) y [la configuración del protocolo](../core/protocol-settings.md) (AS2) que define cómo el perfil de negocio puede enviar o recibir mensajes de otra entidad.  
  
En este tema se muestra cómo crear, ver, editar o eliminar un perfil de negocio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="create-a-business-profile"></a>Crear un perfil de negocio  
  
1.  En **administración de BizTalk Server**, expanda el grupo de BizTalk y seleccione **partes**. 
2. En el **entidades y perfiles empresariales** panel, haga una entidad, seleccione **New**y, a continuación, seleccione **perfil de negocio**.  
  
3.  En el **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escriba un nombre de perfil de negocio.|  
    |**Description**|Escriba una descripción para el perfil de negocio.|  
    |**Propiedades adicionales: nombre / valor**|Escriba un par nombre-valor para almacenar cualquier información sobre la entidad. Puede agregar tantos pares nombre-valor como desee. **Nota:** el servidor BizTalk Server no usa los pares de nombre-valor para ningún proceso; estos datos son solo para fines informativos.|  
    |**Eliminar**|Seleccione esta opción para eliminar el par nombre-valor seleccionado.|  
  
4.  Si es necesario, agregue las identidades de negocio para los perfiles de negocio. En el **identidades** ficha, realice lo siguiente:  
  
    > [!NOTE]
    >  La adición de identidades de negocio en esta fase no es obligatoria. Puede agregar las identidades de negocio más tarde, como parte de un acuerdo para el perfil de negocio. Si decide agregar que identidades de negocio ahora, están disponibles al crear un acuerdo para este perfil de negocio.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Seleccione la celda vacía y, en la cuadrícula de la lista desplegable, seleccione un cuerpo de autenticación que proporcione identidades de negocio únicas a las organizaciones. Por ejemplo, **D-U-N-S (Dun & Bradstreet)**. Dos socios de negocio pueden optar por una identidad de negocio acordada entre ambos. Para estos escenarios, seleccione **definidos mutuamente** (para EDIFACT) o **definidos mutuamente (X12)** (para X12).|  
    |**Qualifier**|Muestra un valor predefinido basado en el valor seleccionado para **nombre**.|  
    |**Valor**|Escriba un valor para la identidad de negocio. Debe tener en cuenta las siguientes consideraciones al proporcionar un valor para las identidades de negocio.<br /><br /> -Para una entidad determinada, puede tener más de un perfil de negocio mediante la misma combinación de nombre de la identidad y el valor de identidad. Por ejemplo, puede tener dos perfiles de negocio para una entidad con **nombre** como **definidos mutuamente (X12)** y **valor** como **THEM**.<br />-Entre entidades, no puede tener dos perfiles de negocio con la misma combinación de nombre de la identidad y el valor de identidad.|  
    |**Quitar**|Seleccione esta opción para quitar la identidad seleccionada.|  
  
5.  Si es necesario, agregue la configuración del protocolo de mensajes con codificación X12, mensajes codificados en EDIFACT o la configuración del protocolo de transporte AS2. Vea [configuración de propiedades de perfil de negocio](../core/configuring-business-profile-properties.md).  
  
6.  Seleccione **aplicar** para aceptar las propiedades o seleccione **Aceptar** para completar la configuración. Cualquiera de estas acciones valida la configuración.  
  
## <a name="view-or-change-a-business-profile"></a>Ver o cambiar un perfil de negocio  
  
1.  En **administración de BizTalk Server**, seleccione **partes**. 

2. En el **entidades y perfiles empresariales** panel, expanda un nodo de entidad para ver los perfiles de negocio en él. Haga clic en un perfil de negocio que desea editar y, a continuación, seleccione **propiedades**.  
  
3.  En el **propiedades de perfil** cuadro de diálogo, vea o edite el perfil. Para obtener información sobre los valores que se pueden especificar en las diferentes páginas en el **propiedades de perfil** cuadro de diálogo, vea [configurar propiedades de perfil de negocio](../core/configuring-business-profile-properties.md).  
  
4.  Seleccione **aplicar** para aceptar las propiedades o seleccione **Aceptar** para completar la configuración. Cualquiera de estas acciones valida la configuración.  

## <a name="delete-a-business-profile"></a>Eliminar un perfil de negocio  
  
1.  En **administración de BizTalk Server**, seleccione **partes**.  
  
3.  En el **entidades y perfiles empresariales** panel, expanda un nodo de entidad para ver los perfiles de negocio en él.  
  
4.  Haga clic en el perfil de negocio que desea eliminar y, a continuación, seleccione **eliminar**. 
  
5.  En el **Confirmar eliminación de perfil de negocio** cuadro de diálogo, seleccione **Sí** para eliminar el perfil de negocio.  


## <a name="see-also"></a>Vea también  
 [Administrar soluciones EDI y AS2](../core/managing-edi-and-as2-solutions.md)
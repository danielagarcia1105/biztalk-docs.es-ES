---
title: Cómo editar las propiedades de una ubicación de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], properties
- managing [receive locations], editing
- receive locations, properties
- receive locations, editing
- editing, receive locations
- editing, properties
ms.assetid: 2b622050-a875-4896-bed6-65ca39a26dd3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578c5e2970e587180a7928563ebdd942c62dc396
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254468"
---
# <a name="how-to-edit-the-properties-of-a-receive-location"></a>Cómo editar las propiedades de una ubicación de recepción
En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para editar las propiedades de una ubicación de recepción que ya existe. Para obtener instrucciones sobre cómo crear una ubicación de recepción, consulte [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-edit-the-properties-of-a-receive-location"></a>Para editar las propiedades de una ubicación de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para el que desea editar las propiedades de una ubicación de recepción y, a continuación, haga clic en **ubicaciones de recepción**.  
  
3.  En el panel derecho, haga clic en la ubicación de recepción y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de la ubicación de recepción** ventana, edite una o varias de las siguientes propiedades y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escribir el nombre de la ubicación de recepción.|  
    |**Tipo**|Seleccionar el tipo de transporte, o protocolo de transporte, en la lista desplegable. Si cambia el tipo de transporte, debe configurar las propiedades de transporte como se describe a continuación.|  
    |**Configurar**|Después de seleccionar el tipo de transporte, haga clic en **configurar** para mostrar la **propiedades de transporte** diálogo cuadro y configure las propiedades de adaptador para la ubicación de recepción. Para obtener instrucciones, haga clic en **ayuda** en el cuadro de diálogo. Para obtener más información acerca de cómo configurar cada tipo de adaptador, vea el tema correspondiente en [usando adaptadores](../core/using-adapters.md).|  
    |**Controlador de recepción**|En la lista desplegable, seleccionar la instancia del host de BizTalk Server en la que se ejecutará la ubicación de recepción. El controlador de recepción debe estar en ejecución en este host.|  
    |**La canalización de recepción**|Seleccionar la canalización de recepción para recibir mensajes en esta ubicación de recepción en la lista desplegable.|  
    |**Canalización de envío**|Seleccionar la canalización de envío para enviar respuesta en esta ubicación de recepción en la lista desplegable. Esta lista sólo está disponible para una ubicación de recepción asociada a un puerto de recepción de solicitud-respuesta.|  
    |**Establecer esta ubicación como principal**|Activar esta casilla si tiene más de una ubicación de recepción para un puerto de recepción y desea que esta ubicación represente el puerto de recepción cuando el puerto deba transferirse a otra entidad, como un socio comercial, que debe enviar mensajes a la organización. La primera ubicación de recepción creada se selecciona automáticamente como la ubicación de recepción primaria. Esta propiedad sigue estando seleccionada y no disponible hasta que designe una ubicación de recepción diferente como primaria.|  
  
> [!NOTE]
>  En caso de cambiar o modificar la ubicación de recepción, reinicie los procesos de trabajo de host aislado correspondientes a la ubicación de recepción modificada.  
  
## <a name="see-also"></a>Vea también  
 [Administrar ubicaciones de recepción](../core/managing-receive-locations.md)
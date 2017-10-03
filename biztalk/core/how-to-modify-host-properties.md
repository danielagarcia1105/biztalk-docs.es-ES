---
title: "Cómo modificar las propiedades de Host | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5df9d7f-b6c2-4bb7-a845-284e6323e3d6
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a5dac64bb50cf84c0d14277687d1641b6fa536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update-host-properties"></a>Actualizar las propiedades de Host

## <a name="overview"></a>Información general
Puede usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para modificar las siguientes propiedades de host:  
  
-   **Grupo de Windows:** los miembros del grupo de Windows tienen permisos para ejecutar los hosts de instancias de este host de forma predeterminada. Si selecciona un grupo de usuarios de Windows para un host de BizTalk, se recomienda que cree un grupo nuevo que esté dedicado a ese host. Si utiliza un grupo existente, asegúrese de que el grupo no tiene más privilegios de los que se necesitan. Para obtener más información, consulte [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md).  
  
    > [!NOTE]
    >  Si cambia la pertenencia a grupo del usuario que tiene una sesión abierta actualmente, y el grupo también pertenece al dominio, debe cerrar la sesión e iniciar otra una vez completados los cambios. Si no lo hace se le denegará el acceso, ya que la nueva pertenencia a grupo no estará reflejada en la sesión actual.  
  
-   **Seguimiento de host:** al menos un host en el grupo debe realizar un seguimiento de estado y los datos económicos. Esta opción indica si el host carga el componente de seguimiento de BizTalk para procesar la supervisión de estado y datos económicos.  
  
    > [!NOTE]
    >  Se recomienda que cree al menos una instancia de host del host de seguimiento. Si no se ejecuta una instancia de host del host de seguimiento, la base de datos de cuadro de mensajes seguirá acumulando datos, lo que causa una degradación en el rendimiento.  
  
     El host que realiza el seguimiento de host tiene acceso de lectura y escritura a las tablas de seguimiento de la base de datos de cuadro de mensajes, así como a la base de datos de seguimiento de BizTalk. Por lo tanto, todos los objetos que se ejecuten en un host que realiza el seguimiento de host tendrán también acceso de lectura y escritura a estas bases de datos. El host que no realice el seguimiento de host solo tiene acceso a las tablas de seguimiento de la base de datos de cuadro de mensajes, pero no tiene acceso a la base de datos de seguimiento de BizTalk.  
  
    > [!NOTE]
    >  Si especifica un host concreto para que realice el seguimiento, afectará al rendimiento de las aplicaciones que se ejecuten en dicho host. Por este motivo, puede ser conveniente crear un host dedicado exclusivamente a permitir el seguimiento de host.  
  
-   **Autenticación de confianza:** puede especificar que BizTalk Server confíe en un host. BizTalk Server confíe en **autenticación de confianza** para colocar el remitente identificador de seguridad (SSID) en los mensajes que el host de confianza pone en cola que se asignan a otros usuarios al host. Para obtener más información acerca de los hosts de autenticación de confianza, consulte [autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md).  
  
     Las instancias de host de hosts de confianza y las instancias de host de hosts que no son de confianza no pueden utilizar las mismas cuentas de servicio. Si desea cambiar la configuración de confianza de una instancia de host y dicha instancia utiliza una cuenta de servicio empleada por otras instancias de host, puede llevar a cabo una de las siguientes acciones:  
  
    -   Puede cambiar la cuenta de servicio de la instancia de host para la que desea cambiar la configuración de confianza a una cuenta de servicio nueva.  
  
    -   Puede cambiar la cuenta de servicio de la instancia de host a una cuenta de servicio existente ya utilizada por otras instancias de host con la misma configuración de confianza.  
  
    -   Puede eliminar la instancia de host y volver a crearla con una configuración de confianza y una cuenta de servicio diferentes.  
  
-   **Host predeterminado del grupo:** debe haber un host predeterminado en el grupo en todo momento. El proceso de alta de orquestación utiliza automáticamente el host predeterminado para alojar la orquestación, a menos que el usuario seleccione explícitamente un host diferente. El primer host creado se marca como host predeterminado. Para obtener información sobre el host predeterminado, consulte [Hosts](../core/hosts.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe disponer de los siguientes derechos de usuario para crear hosts, modificar propiedades de hosts y eliminar hosts:  
  
-   Además, debe ser miembro del grupo de administradores de BizTalk Server. Para obtener información sobre cómo agregar usuarios al grupo de administradores de BizTalk Server, vea [cómo administrar el grupo de administradores de BizTalk Server](../core/how-to-manage-the-biztalk-server-administrators-group.md).  
  
-   Debe disponer de los siguientes derechos en SQL Server:  
  
    -   Debe ser administrador de SQL Server o miembro de las funciones de base de datos db_owner o db_securityadmin de SQL Server en la base de datos de seguimiento de BizTalk (BizTalk DTADb), bases de datos de cuadro de mensajes (BizTalkMsgBoxDb) y la base de datos de importación principal de BAM (BAMPrimaryImport).  
  
    -   Debe ser miembro del rol sysadmin de SQL Server en todos los equipos donde haya bases de datos de cuadro de mensajes, o miembro del rol db_owner o db_ddladmin de SQL Server para todas las bases de datos de cuadro de mensajes.  
  
## <a name="steps"></a>Pasos  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **Hosts**.  
  
3.  En el panel de detalles, haga clic con el host que desea modificar y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades de Host** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Mostrar el nombre de host. Al crearlo, se le asigna un nombre al host.|  
    |**Tipo**|Mostrar el tipo de host. Puede dar de alta una orquestación a un host de tipo En curso y un host de tipo En curso puede contener un controlador de envío. Un host aislado funciona fuera de la instalación de BizTalk Server.|  
  
     **Opciones**  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Permitir seguimiento de Host**|Activar esta casilla para indicar que el host carga el componente de seguimiento de BizTalk para procesar la supervisión de estado y datos empresariales. Si la activa, el host actual tendrá acceso de lectura y escritura a las tablas de seguimiento en la base de datos de cuadro de mensajes, así como en la base de datos de seguimiento. Por tanto, los objetos que se ejecuten en este host tendrán también acceso de lectura y escritura a estas bases de datos. Si la desactiva, el host actual solo tendrá privilegios de escritura para las tablas de seguimiento en la base de datos de cuadro de mensajes y no tendrá acceso a la base de datos de seguimiento.|  
    |**Autenticación de confianza**|Active esta casilla para especificar si BizTalk Server debería confiar en este host.|  
    |**sólo de 32 bits**|Activar esta casilla si desea que el proceso de instancia de host se cree como 32 bits en ambos servidores de 32 y 64 bits. Si esta casilla está desactivada, el proceso de instancia de host se crea como 32 bits en servidores de 32 bits y como 64 bits en servidores de 64 bits.<br /><br /> **Tenga en cuenta** para convertir un proceso de la instancia de host de 32 bits en un proceso de la instancia de host de 64 bits, elimine todas las instancias del host y, a continuación, desactive la **sólo de 32 bits** casilla de verificación. Las instancias del host que cree en un servidor de 64 bits serán de 64 bits.|  
    |**Establecer este host como predeterminado en el grupo**|Activar esta casilla para identificar si este host es el predeterminado. El proceso de alta de orquestación utiliza automáticamente el valor predeterminado host para alojar la orquestación, a menos que seleccione explícitamente un host diferente. Si esta casilla está seleccionada y no está disponible, este host es el predeterminado.|  
    |**Grupo de Windows**|Escribir el grupo local o de dominio para el host. Los miembros del grupo de Windows tendrán permisos para ejecutar instancias de este host.|  
  
5.  En el **certificados** ficha, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Description**|Mostrar una descripción del certificado de descifrado mostrado.|  
    |**Huella digital**|Mostrar la huella digital del certificado de clave privada usado para descifrar los mensajes entrantes para este host. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.|  
    |**Quitar certificado**|Quitar el certificado de descifrado mostrado del host.|  
    |**Examinar**|Haga clic para mostrar la **Seleccionar certificado** cuadro de diálogo donde seleccionar el certificado de descifrado del almacén de certificados equipo Local u otras personas que desea usar con el host.|  
  
## <a name="see-also"></a>Vea también  
-  [Optimizar el uso de recursos mediante la limitación de Host](../core/optimizing-resource-usage-through-host-throttling.md)   
-  [Recomendaciones de diseño de limitación](../core/throttling-design-recommendations.md)   
-  [Administrar hosts de BizTalk e instancias de host](../core/managing-biztalk-hosts-and-host-instances.md)   
-  [Cómo crear un nuevo Host](../core/how-to-create-a-new-host.md)   
-  [Cómo eliminar un Host](../core/how-to-delete-a-host.md)   
-  **MSBTS_Host (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
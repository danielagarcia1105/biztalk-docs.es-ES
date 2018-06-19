---
title: Cree un nuevo Host | Documentos de Microsoft
descriptions: Use BizTalk Administration to create a new host in BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 811e6e57-5c37-471a-aff4-5b2b68c367b1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700f0bb43a4f31b76819e7aca6fe5895cc2b6ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250204"
---
# <a name="create-a-new-host"></a>Cree un nuevo Host
Un host de BizTalk es un contenedor lógico para elementos como controladores de adaptadores, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones. Se recomienda utilizar hosts diferentes para el procesamiento, la recepción y el envío de mensajes, y utilizar también hosts diferentes para elementos de confianza y no de confianza con el fin de facilitar la implementación de medidas de seguridad y facilitar la administración de los hosts. Tan sólo es posible instalar una instancia de un host por cada servidor BizTalk Server. Para obtener más información acerca de los hosts, consulte [Hosts](../core/hosts.md).  
  
 Para obtener información acerca del uso de Windows Management Instrumentation (WMI) para crear un nuevo host, consulte **MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe disponer de los siguientes derechos de usuario para crear hosts, modificar propiedades de hosts y eliminar hosts:  
  
-   Además, debe ser miembro del grupo de administradores de BizTalk Server.  
  
-   Debe disponer de los siguientes derechos en SQL Server:  
  
    -   Debe ser administrador de SQL Server o miembro de las funciones de base de datos db_owner o db_securityadmin de SQL Server en la base de datos de seguimiento de BizTalk (BizTalk DTADb), en las bases de datos de cuadro de mensajes (BizTalkMsgBoxDb) y en la base de datos de importación principal de BAM (BAMPrimaryImport).  
  
    -   Debe ser miembro del rol sysadmin de SQL Server en todos los equipos donde haya bases de datos de cuadro de mensajes, o miembro del rol db_owner o db_ddladmin de SQL Server para todas las bases de datos de cuadro de mensajes.  
  
## <a name="steps"></a>Pasos
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **Hosts**.  
  
3.  En el panel de detalles, haga clic **Hosts**, haga clic en **New**y, a continuación, haga clic en **Host**.  
  
4.  En el **propiedades de Host** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Mostrar el nombre de host. Al crearlo, se le asigna un nombre al host. El nombre de host no puede superar los 80 caracteres.|  
    |**Tipo**|Mostrar el tipo de host. Un host de tipo En curso puede alojar orquestaciones, determinados controladores de envío y recepción. Un host aislado es un límite de procesos externo a BizTalk Server, necesario para algunos controladores de envío y recepción. Puede dar de alta una orquestación en un host de tipo En curso y un host de tipo En curso puede alojar un controlador de envío o recepción.|  
  
     **Opciones**  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Permitir seguimiento de Host**|Activar esta casilla de verificación para indicar el procesamiento de los datos empresariales y la supervisión de estado por parte del host. Si activa esta casilla, el host actual tendrá privilegios de lectura y escritura en las tablas de seguimiento de la base de datos de cuadro de mensajes y en la base de datos de seguimiento de BizTalk. Por tanto, los objetos que se ejecuten en este host tendrán también acceso de lectura y escritura a estas bases de datos. Si desactiva la casilla, el host tendrá sólo acceso de escritura a las tablas de seguimiento de la base de datos de cuadro de mensajes y no tendrá acceso a la base de datos de seguimiento de BizTalk.|  
    |**Autenticación de confianza**|Active esta casilla para especificar si BizTalk Server debería confiar en este host.|  
    |**sólo de 32 bits**|Activar esta casilla de verificación si desea permitir que se cree el proceso de instancia de host de 32 bits en servidores de 32 bits y de 64 bits. Si esta casilla está desactivada, el proceso de instancia de host se crea como 32 bits en servidores de 32 bits y como 64 bits en servidores de 64 bits.|  
    |**Establecer este host como predeterminado en el grupo**|Activar esta casilla para identificar si este host es el predeterminado. Las orquestaciones y los puertos creados utilizan de forma automática el host predeterminado para alojar la orquestación, a menos que seleccione de forma explícita un host distinto. Si esta casilla está seleccionada y no está disponible, este host es el predeterminado.|  
    |**Grupo de Windows**|Escribir el grupo local o de dominio para el host. Los miembros del grupo de Windows tendrán permisos para ejecutar instancias de este host.|  
  
5.  En el **certificados** ficha, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre común**|Mostrar una descripción del certificado de descifrado mostrado.|  
    |**Huella digital**|Mostrar la huella digital del certificado de clave privada usado para descifrar los mensajes entrantes para este host. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.|  
    |**Quitar certificado**|Quitar el certificado de descifrado mostrado del host.|  
    |**Examinar**|Haga clic para mostrar la **la seguridad de Windows** cuadro de diálogo donde seleccionar el certificado de descifrado desde el almacén personal actual que desea utilizar con el host o el usuario actual.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Modificar propiedades de Host](../core/how-to-modify-host-properties.md)   
 [Eliminar un Host](../core/how-to-delete-a-host.md)
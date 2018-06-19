---
title: Cómo modificar las propiedades de grupo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, groups
- configuring, groups
- groups, configuring
- managing [groups], properties
- groups, modifying
- managing [groups], modifying
- groups, properties
ms.assetid: 59e0853d-81b0-43f9-85bf-099868e25fad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a191011b6824086e26c72ce5e5a182a167ca0e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254868"
---
# <a name="how-to-modify-group-properties"></a>Cómo modificar propiedades de grupo
Puede utilizar este procedimiento para configurar propiedades globales para el grupo de BizTalk Server, de manera que se pueda seleccionar un certificado de firma, modificar el intervalo de actualización de la caché y determinar cómo controlará BizTalk Server los mensajes de gran tamaño. Para obtener más información acerca de las propiedades de grupo de BizTalk Server, vea [grupos de BizTalk](../core/biztalk-groups.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-configure-biztalk-group-properties"></a>Para configurar propiedades de grupo BizTalk  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades del grupo de** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escribir el nombre del grupo. El nombre del grupo no puede superar los 128 caracteres. El nombre de este cuadro aparece junto a la **grupo** nodo en el árbol de consola, junto con el nombre del servidor y el nombre de la base de datos de administración de BizTalk.|  
    |**Server**|Mostrar el servidor en el que se almacena físicamente la base de datos de administración de BizTalk.|  
    |**Base de datos**|Mostrar la base de datos de administración de BizTalk en la que se almacena toda la configuración de este grupo.|  
    |**Nombre del servidor de SSO**|Escribir el nombre del servidor de inicio de sesión único (SSO) empresarial que utilizará este equipo para almacenar la información específica de adaptador, así como para obtener acceso a ella. Éste es el nombre del servidor de SSO utilizado para establecer la conexión con la base de datos de SSO.|  
    |**Grupo de administradores de BizTalk**|Mostrar el nombre del grupo de administradores que tiene derechos para administrar el entorno de BizTalk Server después de la instalación.|  
    |**Grupo de operadores de BizTalk**|Muestra el nombre del grupo de operadores que no tiene derechos para ver la configuración, ejecutar consultas y realizar mantenimiento del equipo y la supervisión de aplicaciones básica.|  
    |**Operadores de B2B de BizTalk Server**|Muestra el nombre del grupo de operadores B2B.|  
  
4.  En el **bases de datos** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Bases de datos**|Mostrar los nombres de todas las bases de datos en la aplicación y de todos los servidores en los que residen, tal como se especificó durante la configuración.|  
  
5.  En el **certificado** ficha, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre común**|Ver una descripción del certificado seleccionado.|  
    |**Huella digital**|Mostrar la huella digital del certificado de clave privada que se utiliza para firmar digitalmente los mensajes de salida de este grupo. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la A F.|  
    |**Quitar certificado**|Quitar el certificado que aparece en pantalla.|  
    |**Examinar**|Haga clic para mostrar la **Seleccionar certificado** cuadro de diálogo donde seleccionar el certificado de firma para el usuario actual o el almacén personal que desea usar con el grupo.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de grupos](../core/managing-groups.md)   
 [Grupos de BizTalk](../core/biztalk-groups.md)   
 [Cómo agregar un servidor a un grupo](../core/how-to-add-a-server-to-a-group.md)   
 [Cómo mover un servidor de un grupo a otro](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [Cómo quitar un servidor de un grupo](../core/how-to-remove-a-server-from-a-group.md)
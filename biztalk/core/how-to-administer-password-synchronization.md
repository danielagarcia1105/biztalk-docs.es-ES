---
title: Cómo administrar la sincronización de contraseña | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], applications
- Password Synchronization [SSO], notifications
- applications, Password Synchronization [SSO]
- SSOPS command line utility [SSO]
- administering, Password Synchronization [SSO]
- Password Synchronization [SSO], adapters
- Password Synchronization [SSO], administering
- notifications [SSO]
- Password Synchronization [SSO], SSOPS command line utility
ms.assetid: e5568cc2-7530-452c-9902-d7ffcad66088
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0282b084145db99499c1831e2860934eca44d84a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004685"
---
# <a name="how-to-administer-password-synchronization"></a>Cómo administrar la sincronización de contraseña
La sincronización de contraseñas puede administrarse desde el Complemento MMC o desde la línea de comandos.  
  
 El Complemento MMC muestra una lista de adaptadores y sus propiedades. Puede hacer clic con el botón secundario en un adaptador y utilizar el menú para ejecutar los comandos siguientes:  
  
- Crear adaptadores  
  
- Definir propiedades  
  
- Update  
  
- DELETE  
  
- Habilitar  
  
- Deshabilitar  
  
- Agregar aplicaciones a un adaptador  
  
- Eliminar aplicaciones de un adaptador  
  
- Restablecer una notificación  
  
- Agregar un adaptador a un grupo de adaptadores  
  
- Eliminar un adaptador de un grupo de adaptadores  
  
  También puede utilizar la utilidad de línea de comandos SSOPS para administrar la sincronización de contraseñas. La mayoría de los comandos descritos en esta sección son para uso exclusivo del administrador.  
  
  Para la mayoría de los comandos, la salida de comando se muestra en pantalla, organizada en dos columnas. Puesto que algunos parámetros de pantalla podrían truncar los datos, deberá cambiar el tamaño del búfer de pantalla o el tamaño de Windows a 120 caracteres.  
  
  Los comandos SSOPS se enumeran en la lista tabla siguiente. En sucesivos apartados de este tema se incluyen los procedimientos y su correspondiente explicación.  
  
|Comando|Función|  
|-------------|--------------|  
|-list|Listar los adaptadores existentes|  
|-display|Ver información de adaptadores|  
|-create|Crear adaptadores nuevos|  
|-setprops|Definir las propiedades de un adaptador|  
|-update|Actualizar los adaptadores existentes|  
|-delete|Eliminar un adaptador existente|  
|-enable|Habilitar un adaptador|  
|-disable|Deshabilitar un adaptador|  
|-addapp|Agregar una aplicación a un adaptador|  
|-deleteapp|Eliminar una aplicación de un adaptador|  
|-reset|Restablecer cola de notificaciones o de cambio de contraseñas|  
|-addtogroup|Agregar un adaptador a un grupo de adaptadores|  
|-deletefromgroup|Elimina el adaptador de grupo de adaptadores|  
  
### <a name="to-list-existing-adapters"></a>Para enumerar los adaptadores existentes  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-lista** y presione ENTRAR.  
  
     Aparecerá una lista con los adaptadores y sus descripciones. (E) indica que el adaptador está activado, y (D) indica que está desactivado.  
  
### <a name="to-display-adapter-information"></a>Para ver información de adaptadores  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-mostrar \<nombre de adaptador\>**  y presione ENTRAR.  
  
     La pantalla presentará información detallada del adaptador que se haya especificado.  
  
     Además del nombre, tipo, descripción, equipo y cuentas, se muestra la información siguiente:  
  
    |Indicador del adaptador|Detalles|  
    |------------------|-------------|  
    |Adaptador habilitado|Indica si el adaptador está o no habilitado.<br /><br /> Marca: SSO_FLAG_ENABLED<br /><br /> Nombre de atributo: enableApp<br /><br /> Predeterminado: N|  
    |Permitir grupos locales|Determina si las cuentas App Admin o App Users pueden ser cuentas locales.<br /><br /> Marca: SSO_FLAG_APP_ALLOW_LOCAL<br /><br /> Nombre de atributo: allowLocalAccounts<br /><br /> Predeterminado: N|  
    |Recibir cambios de contraseñas del adaptador|Determina si el adaptador está o no autorizado para recibir cambios de contraseñas externos.<br /><br /> Marca: SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB<br /><br /> Nombre de atributo: syncFromAdapter<br /><br /> Predeterminado: N|  
    |Comprobar contraseña antigua|Determina si el adaptador comprobará la contraseña antigua al recibir un cambio de contraseña externo. Si este indicador está definido con un cambio de contraseña externo, el adaptador externo deberá proporcionar la contraseña antigua, así como la nueva contraseña externa. De esta forma, la contraseña antigua se contrasta con la contraseña externa existente en la base de datos de SSO correspondiente a dicha cuenta. Si las contraseñas coinciden, se aceptará el cambio de contraseña. Si las contraseñas no coinciden, se denegará el cambio de contraseña.<br /><br /> Marca: SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS<br /><br /> Nombre de atributo: verifyOldPassword<br /><br /> Predeterminado: Sí|  
    |Cambiar la contraseña de Windows|Determina si también se debe cambiar la contraseña de Windows al recibir un cambio de contraseña externo (sincronización completa). ENTSSO utiliza siempre la contraseña antigua de Windows, almacenada en la base de datos de SSO, para cambiar la contraseña de Windows por el valor nuevo (para el cambio de la contraseña de usuario, Windows solicita la contraseña antigua y la nueva). Por lo tanto, este valor deberá inicializarse para que el cambio de contraseña de Windows se efectúe correctamente. Si se configura la sincronización de contraseña para una asignación determinada, a continuación, cuando se establecen las credenciales externas a través de herramientas administrativas (ssomanage o ssoclient - setcredentials) la contraseña de Windows almacenada en la base de datos SSO también se establecerá. Marca: SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS<br /><br /> Nombre de atributo: changeWindowsPassword<br /><br /> Predeterminado: N|  
    |Enviar cambios de contraseñas de Windows al adaptador|Determina si los cambios de contraseña de Windows deben o no enviarse al adaptador externo.<br /><br /> Marca: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL<br /><br /> Nombre de atributo: syncToAdapter<br /><br /> Predeterminado: N|  
    |Enviar contraseña antigua al adaptador|Si se define como Sí, el valor de la contraseña antigua (procedente de la base de datos de SSO) también se enviará al adaptador externo, junto con el nuevo valor de contraseña. Algunos sistemas externos podrían solicitar ambos valores (contraseña antigua y contraseña nueva) para efectuar un cambio de contraseña.<br /><br /> Marca: SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS<br /><br /> Nombre de atributo: sendOldPassword<br /><br /> Predeterminado: N|  
    |Permitir conflictos de asignación|Determina si el adaptador debe o no permitir los conflictos de asignación.<br /><br /> Los conflictos de asignación tienen lugar cuando las asignaciones no son exclusivas. En una aplicación de SSO Individual, las asignaciones siempre son uno a uno: una cuenta de Windows se asigna exactamente a una cuenta externa y viceversa.<br /><br /> Sin embargo, es posible asignar más de una aplicación a un mismo adaptador. Por lo tanto, existe la posibilidad de que la asignación de una aplicación entre en conflicto con otra.<br /><br /> La finalidad de este indicador consiste en evitar que esto suceda. Resulta más seguro no permitir los conflictos de asignación, a menos que exista un requisito específico y justificado para hacerlo.<br /><br /> Marca: SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS<br /><br /> Nombre de atributo: allowMappingConflicts<br /><br /> Predeterminado: N|  
  
    |Descripción del adaptador|Detalles|  
    |-------------------------|-------------|  
    |Número de reintentos de notificación|El valor predeterminado es 1.|  
    |Intervalo entre reintentos de notificación (en minutos)|El valor predeterminado es 5.|  
    |Número máximo de notificaciones pendientes|El valor predeterminado es 8.|  
    |Almacenar notificaciones (sin conexión)|True/False|  
    |Nombre del servidor|Nombre de servidor.|  
    |Número de puerto|Número de puerto.|  
    |Aplicaciones para este adaptador|Ofrece una lista de las aplicaciones actualmente asignadas al adaptador.|  
  
### <a name="to-create-new-adapters"></a>Para crear un adaptador nuevo  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-crear \<adaptador archivo\>**  y presione ENTRAR.  
  
     La pantalla presentará información detallada del adaptador que se acaba de crear.  
  
### <a name="to-set-properties-for-an-adapter"></a>Para establecer las propiedades de un adaptador  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops - setprops \<nombre de adaptador\>**  y presione ENTRAR.  
  
     La pantalla presentará las propiedades del adaptador que se haya especificado. Si es necesario, puede editarlas, aunque los valores nuevos no se validarán.  
  
### <a name="to-update-existing-adapters"></a>Para actualizar los adaptadores existentes  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-update \<adaptador archivo\>**  y presione ENTRAR.  
  
     Utilice este comando para actualizar los parámetros e indicadores de un adaptador concreto. No utilice este comando para la definición de propiedades. En su lugar, utilice -setprops.  
  
### <a name="to-delete-an-existing-adapter"></a>Para eliminar un adaptador existente  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-delete \<nombre de adaptador\>**  y presione ENTRAR.  
  
     El adaptador especificado se eliminará.  
  
### <a name="to-enable-an-adapter"></a>Para habilitar un adaptador  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-habilitar \<nombre de adaptador\>**  y presione ENTRAR.  
  
     El adaptador especificado quedará habilitado.  
  
### <a name="to-disable-an-adapter"></a>Para deshabilitar un adaptador  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-deshabilitar \<nombre de adaptador\>**  y presione ENTRAR.  
  
     El adaptador especificado quedará deshabilitado.  
  
### <a name="to-add-an-application-to-an-adapter"></a>Para agregar una aplicación a un adaptador  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops - addapp \<nombre de adaptador\> \<nombre de la aplicación\>**  y presione ENTRAR.  
  
     La aplicación de SSO especificada quedará asignada al adaptador especificado. Esto significa que las contraseñas de las asignaciones de dicha aplicación no se sincronizarán con este adaptador.  
  
     Mientras que un adaptador puede tener asignadas varias aplicaciones, una aplicación puede tener asignado un solo adaptador.  
  
### <a name="to-delete-an-application-from-an-adapter"></a>Para eliminar una aplicación de un adaptador  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops - deleteapp \<nombre de la aplicación\>**  y presione ENTRAR.  
  
     La aplicación de SSO especificada quedará eliminada del adaptador especificado. Puesto que una aplicación sólo puede tener asignado un adaptador, no será necesario especificar el nombre del adaptador.  
  
### <a name="to-reset-notification"></a>Para restablecer una notificación  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops-restablecer \<nombre de adaptador &#124; todas &#124; amortiguación\>**  y presione ENTRAR.  
  
     Este comando deja vacías la cola de la tabla histórica de cambios de contraseñas y la cola de notificaciones de uno adaptador o de todos, según se especifique. La tabla histórica de cambios de contraseñas almacena un historial de cambio de contraseñas cada 10 minutos. Antes de aceptar o enviar un cambio de contraseña, el sistema de SSO empresarial verifica la tabla histórica de cambios de contraseñas para comprobar si se ha efectuado dicho cambio recientemente. Si es así, la contraseña nueva queda descartada.  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a>Para agregar un adaptador a un grupo de adaptadores  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops - addtogroup \<nombre de adaptador\> \<grupo de adaptadores\>**  y presione ENTRAR.  
  
     Este comando permite agregar el adaptador especificado al grupo de adaptadores especificado. Mientras que un adaptador puede pertenecer a un solo grupo de adaptadores, un grupo de adaptadores puede contener varios adaptadores.  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a>Para eliminar un adaptador de un grupo de adaptadores  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssops - deletefromgroup \<nombre de adaptador\> \<grupo de adaptadores\>**  y presione ENTRAR.  
  
     Este comando permite eliminar el adaptador especificado del grupo de adaptadores especificado.  
  
## <a name="see-also"></a>Vea también  
 [Sincronización de contraseñas](../core/password-synchronization2.md)
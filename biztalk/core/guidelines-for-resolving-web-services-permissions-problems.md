---
title: Directrices para solucionar problemas de permisos de los servicios Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e29543e9-9b87-437b-ac91-8f1cce01fab4
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68fc866a2a1f2c51a0649cf8a01ef03164b9a913
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246780"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a>Directrices para solucionar problemas de permisos de servicios web
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suele usar servicios web junto con el adaptador de SOAP, así como al publicar orquestaciones como servicios web. Este tema proporciona directrices generales para minimizar los problemas con los permisos de servicios Web, así como pasos que pueden seguirse para resolver los problemas de ese tipo que afecten a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="general-guidelines"></a>Directrices generales  
  
-   **Configurar cuentas de usuario**: asegúrese de que la identidad de proceso de host de aplicación IIS asociada con el directorio virtual que hospeda el servicio Web se establece en una cuenta de usuario y asegúrese de que esta cuenta de usuario se agrega a los grupos siguientes:  
  
    -   Usuarios de hosts aislados de BizTalk (dominio o grupo local)  
  
    -   IIS_WPG (grupo local)  
  
     La pertenencia a estos 2 grupos es necesaria para conceder al servicio Web creado por el Asistente para publicar servicios Web de BizTalk los derechos apropiados para publicar un mensaje de solicitud SOAP en la base de datos de cuadro de mensajes de BizTalk, lo que a su vez activará la orquestación de suscripción. Para obtener más información sobre cómo determinar o establecer la identidad de proceso de host de aplicación de IIS, consulte la **identidad de proceso de Host de aplicación de configuración de IIS** sección de [directrices para resolver problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md).  
  
-   **Establecer permisos en la carpeta especificada por la variable de entorno TEMP**: asegúrese de que ha leído la identidad de proceso de host de aplicación de IIS para el directorio virtual que hospeda el servicio Web y permisos de escritura para la carpeta especificada por el Variable de entorno TEMP. Para determinar la carpeta especificada por la variable de entorno TEMP, abra un símbolo del sistema en BizTalk Server, escriba el comando siguiente y presione ENTRAR:  
  
    ```  
    echo %TEMP%  
    ```  
  
     La carpeta especificada por la variable de entorno TEMP es el lugar en que el servicio Web se compila en modo Just In Time (JIT) para generar un archivo de biblioteca de vínculos dinámicos (dll), y por tanto debe ser accesible con permisos de lectura y escritura por esta cuenta de usuario.  
  
-   **Envío de credenciales en la llamada al método SOAP**: asegúrese de que el cliente del servicio Web está enviando credenciales en la llamada al método SOAP. De forma predeterminada, IIS 7.0 en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] requiere autenticación de Windows. Al probar un servicio Web con Internet Explorer, las credenciales del usuario que ha iniciado la sesión se envían automáticamente. Este es el motivo por el que el servicio Web puede funcionar desde Internet Explorer pero produce errores desde otro cliente. Si el cliente del servicio Web no agrega credenciales a la llamada al método SOAP, se generará una excepción SOAP debido a un error de autenticación. Para obtener más información acerca de cómo enviar credenciales en un método SOAP llamada vea el código de ejemplo disponible en [cómo usar las nuevas clases de System.Net para crear un cliente HTTP](http://support.microsoft.com/kb/303436).  
  
-   **Solución de problemas de errores de llamadas a un servicio Web**: si se producen errores al llamar a un servicio Web, compruebe el registro de aplicación o mensaje de seguimiento de instancias de servicio y eventos a través de la administración de BizTalk Server **concentrador de grupo**página. Para obtener más información sobre las posibles causas del error, consulte [supervisar BizTalk Server](../core/monitoring-biztalk-server.md) y [mediante la página concentrador de grupo](../core/using-the-group-hub-page.md).  
  
-   **Recopilar información de depuración**: para obtener información de depuración detallada, siga los pasos descritos en el tema [depurar servicios Web publicados](../core/debugging-published-web-services.md) si sigue los pasos anteriores no resuelven el problema.  
  
## <a name="known-issues"></a>Problemas conocidos  
 Para obtener información adicional sobre problemas conocidos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relativos a los permisos de servicios Web, vea "No se puede llamar a una orquestación que se expone como un servicio Web en un servidor que ejecuta BizTalk Server" en [http://go.microsoft.com/ ¿fwlink /? LinkId = 196379](http://go.microsoft.com/fwlink/?LinkId=196379).  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas de permisos de servidor BizTalk Server](../core/troubleshooting-biztalk-server-permissions.md)   
 [Directrices para solucionar problemas de permisos de IIS](../core/guidelines-for-resolving-iis-permissions-problems.md)
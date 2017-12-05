---
title: "Prácticas recomendadas para administrar Certificates2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71fa00cc-2e0c-46b3-ae62-f130a5b5f4f5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb6550a5e7b3604d4bb99507299cce5262e210e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="best-practices-for-managing-certificates"></a>Prácticas recomendadas para la administración de certificados
Esta sección proporciona prácticas recomendadas para administrar certificados en el entorno de Microsoft BizTalk Server.  
  
## <a name="assess-and-plan-your-use-of-certificates"></a>Evaluar y planear el uso de certificados  
 **Realizar un análisis de modelo de amenazas de su entorno**  
  
-   Lleve a cabo un análisis de modelo de amenazas (TMA) de su entorno para determinar si los certificados de firma o cifrado contribuirán a minimizar las amenazas para la seguridad.  
  
 **Crear un plan para certificados de clave pública con socios comerciales**  
  
-   Crear un plan para los certificados de clave pública para enviar y recibir certificados de clave pública de socios. Si no utiliza certificados de firma para la resolución de entidades, el certificado público puede adjuntarse al mensaje, en cuyo caso no se necesitará una copia del certificado de antemano en su sistema.  
  
 **Establezca directrices con socios comerciales para el envío de claves públicas**  
  
-   Como parte del contrato de nivel de servicio (SLA) con el socio comercial, establezca directrices para el envío de claves públicas, con lo que se le notificará el momento de revocación y de inminente caducidad de los certificados.  
  
## <a name="install-certificates"></a>Instalar certificados  
 **Descargar la lista de revocación de certificados a intervalos establecidos**  
  
-   Descargue la lista de revocaciones de certificados (CRL) de su entidad emisora de certificados (CA) a intervalos determinados. Se recomienda llevar esto a cabo una vez a la semana. Las CRL se descargan automáticamente si hay una CA para el dominio al que se han unido los servidores BizTalk Server.  
  
 **Comprobar los certificados de firmas**  
  
-   Asegúrese de efectuar una comprobación de los certificados de firma con respecto a la lista de revocación de certificados. Para obtener más información acerca de cómo comprobar los certificados de firma, vea [cómo configurar el componente de canalización de descodificador MIME/SMIME](http://go.microsoft.com/fwlink/?LinkId=155145) (http://go.microsoft.com/fwlink/?LinkId=155145) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 **Administrar certificados con socios comerciales**  
  
-   Haga que la administración de certificados forme parte de las prácticas de administración de socios comerciales. Al agregar una entidad al entorno de BizTalk Server o quitarla de éste, resulta recomendable agregar o quitar certificados asociados con el socio comercial.  
  
 **Quite certificados antes de quitar una instancia de host**  
  
-   Antes de quitar una instancia de host de un servidor BizTalk Server, quite los certificados del almacén personal de la cuenta en la que se ejecuta la instancia de host.  
  
## <a name="configure-biztalk-server-to-use-certificates-for-mimesmime"></a>Configurar BizTalk Server para usar certificados de MIME/SMIME  
 **Evite la denegación de ataques de servicio para las firmas digitales**  
  
-   Determine qué desea hacer con los mensajes cuando el servidor BizTalk Server no se puede validar la firma digital. Establecer la propiedad de autenticación en el puerto de recepción le ayudará a evitar la denegación de servicio ataques.  
  
    > [!NOTE]  
    >  La autenticación - quitar mensajes y autenticación - mantener mensajes marcas en el puerto de recepción requieren que el componente de canalización de resolución de entidades se ha configurado correctamente y que las entidades se definan en BizTalk Server. Para obtener más información, consulte [componente de canalización de resolución de entidades](http://go.microsoft.com/fwlink/?LinkId=155146) (http://go.microsoft.com/fwlink/?LinkId=155146) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
 **Crear diferentes ubicaciones de recepción de mensajes cifrados y sin cifrar**  
  
-   Si planea recibir mensajes con cifrado MIME de algunos socios comerciales y mensajes sin cifrar de otros, cree ubicaciones de recepción independientes en hosts diferentes para mensajes cifrados y sin cifrar. Cuando se espera que sólo los mensajes cifrados con MIME, configure la opción de permitir mensaje no MIME en el componente de canalización de descodificación MIME/SMIME en no.  
  
## <a name="configure-a-biztalk-adapter-to-use-certificates"></a>Configurar un adaptador de BizTalk para utilizar certificados  
 **Pruebe la conexión al sitio Web de destino**  
  
-   Si está usando SSL, asegúrese de que puede conectarse al sitio Web de destino con Microsoft Internet Explorer® antes de intentar conectarse al sitio Web de destino con los transportes HTTP o SOAP. Compruebe que ningún cuadro de diálogo se muestran en el Explorador de Internet cuando se conecta al sitio Web de destino. BizTalk Server no dispone de mecanismos para interactuar con los cuadros de diálogo que pueden aparecer al conectarse al sitio web de destino. Un cuadro de diálogo puede mostrarse de Internet Explorer si el nombre del sitio Web de destino no coincide con el nombre especificado para el sitio Web en el certificado SSL o si la entidad de certificación de raíz para el certificado SSL no está en la certificación de raíz de confianza adecuado Almacén de entidades.  
  
 **Utilice la herramienta de diagnóstico de SSL para analizar problemas de conexión de SSL**  
  
-   La herramienta de diagnóstico de SSL es un componente opcional del Kit de herramientas de diagnóstico de IIS. Puede descargar el Kit de herramientas de diagnóstico de IIS desde la [herramientas de diagnóstico de Internet Information Services](http://go.microsoft.com/fwlink/?LinkID=64426) página (http://go.microsoft.com/fwlink/?LinkID=64426).  
  
## <a name="exporting-a-certificate-from-one-biztalk-group-to-another"></a>Exportar un certificado desde un grupo de BizTalk a otro  
 **Asegúrese de que se está usando un certificado importado para el propósito planteado**  
  
-   Si importa un certificado en un grupo, el certificado importado debe tener una propiedad de uso que es coherente con su uso previsto. Para comprobar la propiedad de uso, haga doble clic en el certificado en el **consola de administración de certificados** de interfaz y, a continuación, haga clic en el **detalles** pestaña de la **certificado** cuadro de diálogo. A continuación, haga clic en el **todos los** opción para la **mostrar** lista desplegable y, a continuación, haga clic para seleccionar la **EKU** o **uso mejorado de clave** campos Para comprobar el fin previsto. Si BizTalk Server intenta usar un certificado para que no sea su propósito, se producirá un error en tiempo de ejecución.
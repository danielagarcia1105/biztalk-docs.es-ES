---
title: Procedimientos recomendados para administrar Certificates2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71fa00cc-2e0c-46b3-ae62-f130a5b5f4f5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e2b79e2a0d7e4758ac87503f4bfac122c9ee215
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994789"
---
# <a name="best-practices-for-managing-certificates"></a>Prácticas recomendadas para la administración de certificados
Esta sección proporciona procedimientos recomendados para administrar certificados en su entorno de Microsoft BizTalk Server.  
  
## <a name="assess-and-plan-your-use-of-certificates"></a>Evaluar y planear el uso de certificados  
 **Realizar un análisis de modelo de amenazas de su entorno**  
  
- Lleve a cabo un análisis de modelo de amenazas (TMA) de su entorno para determinar si los certificados de firma o cifrado contribuirán a minimizar las amenazas para la seguridad.  
  
  **Crear un plan para certificados de clave pública con socios**  
  
- Cree un plan para los certificados de clave pública para enviar y recibir certificados de clave pública de asociados. Si no utiliza certificados de firma para la resolución de entidades, el certificado público puede adjuntarse al mensaje, en cuyo caso no se necesitará una copia del certificado de antemano en su sistema.  
  
  **Establezca directrices con socios para el envío de claves públicas**  
  
- Como parte del contrato de nivel de servicio (SLA) con el socio comercial, establezca directrices para el envío de claves públicas, con lo que se le notificará el momento de revocación y de inminente caducidad de los certificados.  
  
## <a name="install-certificates"></a>Instalar certificados  
 **Descargar la lista de revocación de certificados a intervalos establecidos**  
  
- Descargue la lista de revocaciones de certificados (CRL) de su entidad emisora de certificados (CA) a intervalos determinados. Se recomienda llevar esto a cabo una vez a la semana. Las CRL se descargan automáticamente si hay una CA para el dominio al que se han unido los servidores BizTalk Server.  
  
  **Comprobar los certificados de firmas**  
  
- Asegúrese de efectuar una comprobación de los certificados de firma con respecto a la lista de revocación de certificados. Para obtener más información sobre cómo comprobar los certificados de firma, vea [cómo configurar el componente de canalización de descodificador MIME/SMIME](http://go.microsoft.com/fwlink/?LinkId=155145) (<http://go.microsoft.com/fwlink/?LinkId=155145>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
  **Administrar certificados con socios**  
  
- Haga que la administración de certificados forme parte de las prácticas de administración de socios comerciales. Al agregar una entidad al entorno de BizTalk Server o quitarla de éste, resulta recomendable agregar o quitar certificados asociados con el socio comercial.  
  
  **Quite certificados antes de quitar una instancia de host**  
  
- Antes de quitar una instancia de host de un servidor BizTalk Server, quite los certificados del almacén personal de la cuenta en la que se ejecuta la instancia de host.  
  
## <a name="configure-biztalk-server-to-use-certificates-for-mimesmime"></a>Configurar BizTalk Server para usar certificados de MIME/SMIME  
 **Evitar la denegación de servicio para las firmas digitales**  
  
- Determine qué desea hacer con los mensajes al servidor BizTalk Server no se puede validar la firma digital. Establecer la propiedad de autenticación en el puerto de recepción para evitar la denegación de servicio.  
  
  > [!NOTE]
  >  La autenticación - quitar mensajes y autenticación - mantener mensajes marcas en el puerto de recepción requieren que el componente de canalización de resolución de entidades se ha configurado correctamente y que las entidades se definan en BizTalk Server. Para obtener más información, consulte [componente de canalización de resolución de entidad](http://go.microsoft.com/fwlink/?LinkId=155146) (<http://go.microsoft.com/fwlink/?LinkId=155146>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
  **Crear diferentes ubicaciones de recepción de mensajes cifrados y sin cifrar**  
  
- Si planea recibir mensajes con cifrado MIME de algunos socios comerciales y mensajes sin cifrar de otros, cree ubicaciones de recepción independientes en hosts diferentes para mensajes cifrados y sin cifrar. Cuando se espera que sólo los mensajes cifrados con MIME, configure la opción de permitir mensaje no MIME en el componente de canalización de descodificación MIME/SMIME en no.  
  
## <a name="configure-a-biztalk-adapter-to-use-certificates"></a>Configurar un adaptador de BizTalk para utilizar certificados  
 **Probar la conexión al sitio Web de destino**  
  
- Si está usando SSL, asegúrese de que puede conectar al sitio Web de destino con Microsoft Internet Explorer® antes de intentar conectarse al sitio Web de destino con los transportes HTTP o SOAP. Compruebe que no se muestra ningún cuadro de diálogo en Internet Explorer cuando se conecta al sitio Web de destino. BizTalk Server dispone de ningún mecanismo para interactuar con los cuadros de diálogo que pueden aparecer al conectarse al sitio web de destino. Un cuadro de diálogo debe mostrarse por Internet Explorer si el nombre del sitio Web de destino no coincide con el nombre especificado para el sitio Web en el certificado SSL o si la entidad de certificación raíz para el certificado SSL no está en la certificación de raíz de confianza adecuado Almacén de entidades.  
  
  **Utilice la herramienta de diagnóstico de SSL para analizar los problemas de conexión de SSL**  
  
- La herramienta de diagnóstico de SSL es un componente opcional del Kit de herramientas de diagnóstico de IIS. Puede descargar el Kit de herramientas de diagnóstico de IIS desde la [herramientas de diagnóstico de Internet Information Services](http://go.microsoft.com/fwlink/?LinkID=64426) página (http://go.microsoft.com/fwlink/?LinkID=64426).  
  
## <a name="exporting-a-certificate-from-one-biztalk-group-to-another"></a>Exportar un certificado de un grupo de BizTalk a otro  
 **Asegúrese de que está utilizando un certificado importado para su finalidad prevista**  
  
-   Si importa un certificado en un grupo, el certificado importado debe tener una propiedad de uso que sea coherente con su uso previsto. Para comprobar la propiedad de uso, haga doble clic en el certificado en el **consola de administración de certificados** interfaz y, a continuación, haga clic en el **detalles** pestaña de la **certificado** cuadro de diálogo. A continuación, haga clic en el **todos los** opción para la **mostrar** lista desplegable y, a continuación, haga clic para seleccionar el **uso clave** o **uso mejorado de clave** campos Para comprobar la finalidad prevista. Si BizTalk Server intenta usar un certificado para que no sea su finalidad prevista, se producirá un error en tiempo de ejecución.
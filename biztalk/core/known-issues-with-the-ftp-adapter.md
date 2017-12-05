---
title: Problemas conocidos con el adaptador de FTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e58f2db-9ec5-41fe-af02-9a7d60a217db
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13ce12e8514eaa2b5843ba81eff4f505e65d9e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-the-ftp-adapter"></a>Problemas conocidos del adaptador de FTP
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a>Puede que se dupliquen o se pierdan datos cuando reciba datos en BizTalk Server mediante el adaptador de FTP.  
  
##### <a name="problem"></a>Problema  
 Se duplican o se pierde cuando se reciben los datos en datos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de FTP.  
  
##### <a name="cause"></a>Causa  
 El adaptador de FTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el protocolo de cliente de FTP para sondear el servidor FTP designado y recupera datos del servidor “como tal”. El adaptador de FTP no valida los datos que recupera. El adaptador de FTP envía el documento recuperado al motor de mensajería de BizTalk para procesarlo y luego elimina el documento original desde el servidor FTP. Si el adaptador de FTP recupera un documento del servidor FTP que todavía está escribiendo la aplicación de host, el documento recuperado estará incompleto. Si el adaptador de FTP recupera una copia incompleta del documento original, puede que se produzca la duplicación o pérdida de datos en los escenarios siguientes:  
  
-   Si la aplicación de host todavía está escribiendo el documento original en el servidor FTP, el adaptador de FTP no podrá eliminar el documento y recuperará otra copia del documento en el intervalo de sondeo que está configurado para la ubicación de recepción. De este modo se produce la duplicación del documento.  
  
-   Si la aplicación de host ha terminado de escribir el documento en el servidor FTP, el documento se eliminará. De este modo se produce la pérdida de datos.  
  
##### <a name="resolution"></a>Solución  
 Para solucionar este comportamiento, utilice uno de los métodos siguientes:  
  
-   Configure la aplicación de host para escribir en una carpeta temporal del mismo disco duro que la carpeta pública de FTP y mueva periódicamente el contenido de la carpeta temporal a la carpeta de FTP. La carpeta temporal debe estar en el mismo disco duro que la carpeta pública de FTP para garantizar que la operación de desplazamiento sea atómica. Una operación atómica es una operación funcionalmente indivisible. Si escribir datos en la carpeta pública de FTP mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adaptador de FTP, puede hacerlo mediante la especificación de una propiedad de la carpeta temporal en el cuadro de diálogo Propiedades de transporte FTP cuando se configura un puerto de envío. Si especifica una propiedad de carpeta temporal, asegúrese de que esta carpeta reside en el mismo disco físico que la carpeta pública de FTP.  
  
-   Configure la ubicación de recepción FTP para operar en una ventana de servicio cuando la aplicación de host no escriba datos en el servidor FTP. Puede determinar la ventana de servicio cuando configura las propiedades de ubicación de recepción.  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a>El adaptador FTP no admite la comprobación de revocaciones en los certificados del servidor  
  
##### <a name="problem"></a>Problema  
 El adaptador de FTP en BizTalk Server se ha mejorado para admitir la transferencia de archivos de forma segura a y desde un servidor FTPS mediante SSL/TLS. La lista de revocación de certificados (CRL) contiene una lista de certificados que se han revocado y que ya no son válidos. El adaptador FTP no consulta la CRL para autenticar el certificado de servidor.  
  
##### <a name="cause"></a>Causa  
 Por diseño, el adaptador FTP no consulta la CRL antes de aceptar un certificado de servidor.  
  
##### <a name="resolution"></a>Solución  
 Se requiere; ninguna acción Este comportamiento es así por diseño.  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a>El adaptador FTP descarga archivos más grandes que el tamaño máximo de archivo  
  
##### <a name="problem"></a>Problema  
 El adaptador de recepción FTP descarga archivos cuyo tamaño es mayor que el especificado en la propiedad de tamaño máximo de archivo de los siguientes servidores FTP:  
  
-   AIX  
  
-   MVS  
  
-   AS400  
  
-   GXS  
  
##### <a name="cause"></a>Causa  
 Por diseño, el adaptador FTP no respeta el tamaño máximo de archivo al descargar archivos de estos servidores FTP.  
  
##### <a name="resolution"></a>Solución  
 Se requiere; ninguna acción Este comportamiento es así por diseño.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción de FTP](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3)   
 [Solucionar problemas del adaptador FTP](../core/troubleshooting-the-ftp-adapter.md)
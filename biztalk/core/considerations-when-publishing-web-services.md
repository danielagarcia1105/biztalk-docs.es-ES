---
title: Consideraciones al publicar servicios Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, planning
- Web services, schemas
- schemas, Web services
ms.assetid: 3ace0260-a1cb-4e59-a820-36ee7d5cceda
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825a16555f0b0c82282ae4d85592567d2a19c073
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-publishing-web-services"></a>Consideraciones al publicar servicios web
En este tema se proporciona información que debe tener en cuenta antes de publicar servicios Web.  
  
## <a name="publishing-schemas-and-the-include-element"></a>Publicar esquemas y el elemento include  
 Hay algunos escenarios donde los esquemas que contienen el **incluyen** elemento no se pueden publicar como un servicio Web. Se producirá un error al finalizar el Asistente para publicación de servicios Web de BizTalk. Entre estas restricciones se incluyes las siguientes:  
  
-   Incluyen circulares (el esquema incluido tiene un **incluyen** elemento en el esquema de inclusión)  
  
-   Un sin resolver **schemaLocation** atributo producirá un error  
  
 Para obtener más información acerca del límite del elemento include, vea "Include Element Binding Support" en [http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312).  
  
## <a name="publishing-schemas-and-the-import-element"></a>Publicar esquemas y el elemento import  
 El Asistente para publicar servicios Web de BizTalk Server tiene la misma limitación que el XSD.exe incluido en .NET Framework. Para obtener más información, vea "Import Element Binding Support" en [http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311).  
  
## <a name="publishing-schemas-and-the-redefine-element"></a>Publicar esquemas y el elemento redefine  
 El Asistente para publicar servicios Web de BizTalk Server tiene la misma limitación que el XSD.exe incluido en .NET Framework. Para obtener más información, consulte "Redefine Element Binding Support" en [http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313).  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a>Publicar esquemas que especifiquen valores para los atributos minOccurs o maxOccurs  
 Si publica un esquema que contiene **minOccurs** o **maxOccurs** atributos con valores específicos, estos valores pueden ser diferentes en el esquema expuesto por el servicio Web publicado. Como regla general, todos los atributos minOccurs están convertidos a 0 (minOccurs=0), y los atributos maxOccurs están convertidos a 1 o están sin enlazar (maxOccurs=1 o maxOccurs=sin enlazar).  
  
## <a name="publishing-envelope-schemas"></a>Publicar esquemas de sobre  
 Si dispone de un esquema de sobres que va a publicar como servicio Web, debe modificar manualmente el proyecto Web que se genera.  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>Para modificar el proyecto Web generado de los esquemas de sobres  
  
1.  Abra el archivo <`myWebService`>.asmx.cs.  
  
2.  Edite el archivo y cambie `bodyTypeAssemblyQualifiedName = <dll.name.version.>` a `bodyTypeAssemblyQualifiedName = null`.  
  
> [!NOTE]
>  Puede tener que restablecer los Servicios de Internet Information Server (IIS) si el archivo .dll anterior se encuentra aún en el proceso de trabajo de ASPNET.  
  
## <a name="web-service-and-web-method-attributes"></a>Atributos de métodos Web y de servicios Web  
 El Asistente para publicar servicios Web de BizTalk no permite personalizar el servicio Web ni los atributos de métodos Web usados en ASP.NET. Algunos atributos se establecen automáticamente en función de la información que proporciona el asistente. El asistente no usa los otros atributos.  
  
 La modificación de los atributos existentes o la agregación de nuevos atributos a servicios Web generados por el Asistente para publicar servicios Web de BizTalk puede provocar que el servicio Web no funcione correctamente.  
  
 Para obtener más información acerca de los atributos de método Web y servicios Web, consulte el **WebServiceAttribute** y **WebMethodAttribute** clases en la documentación de .NET Framework SDK.  
  
## <a name="web-method-required"></a>Método Web necesario  
 Un servicio Web debe tener como mínimo un método Web. Sin por lo menos un método Web, las operaciones de los tipos de puertos no se crearán. XLANG/s no admite tipos de puertos que no tengan operaciones.  
  
## <a name="dbcs-character-support"></a>Compatibilidad de caracteres de DBCS  
 Los servicios Web no admiten caracteres de extensión A de ideogramas unificados de chino/japonés/coreano (CJK).  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a>Volver a publicar servicios Web mediante el Asistente para publicación de servicios Web de BizTalk  
 Puede usar el Asistente para publicación de servicios Web de BizTalk para crear un servicio Web publicado. En el **Web *** servicio *** proyecto** página, puede seleccionar la **sobrescribir *** Web *** servicio** opción.  
  
 El asistente no almacena la configuración usada anteriormente. Si realiza cambios en la configuración al volver a ejecutar el asistente, puede producirse un error en cualquiera de los clientes Web que consuman el servicio Web publicado (o lo llamen). Debe actualizar las referencias Web de los clientes que consuman un servicio Web que se ha vuelto a publicar (o lo llamen).  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a>Puede que los clientes de los servicios Web publicados no reciban errores de tiempo de espera de la secuencia de comandos de servidor  
 Servicios Web generados con el Asistente de publicación de servicios Web en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] están configurados de forma predeterminada con un valor de tiempo de espera de secuencia de comandos de **110** segundos. Éste es el valor predeterminado para la propiedad **HttpServerUtility.ScriptTimeout** propiedad. Los clientes Web que utilizan .NET Framework se configuran de forma predeterminada con un valor de tiempo de espera de solicitud de **100** segundos. Este es el valor predeterminado para .NET Framework **HttpWebRequest.Timeout** propiedad.  
  
 Si los clientes Web que utilizan .NET Framework efectúan llamadas a un servicio Web generado con el Asistente para publicación de servicios Web de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible que el cliente no pueda recibir errores de tiempo de espera de la secuencia de comandos de servidor, ya que el tiempo de espera de solicitud del cliente se produce en primer lugar de forma predeterminada. Para resolver el problema, puede llevar a cabo uno de los siguientes procedimientos:  
  
-   Aumentar el tiempo de espera de solicitud de cliente a un valor mayor que el tiempo de espera de secuencia de comandos de servidor si aumenta el valor de la **HttpWebRequest.Timeout** propiedad en el cliente.  
  
-   Reducir el tiempo de espera de secuencia de comandos de servidor en un valor menor que el tiempo de espera de solicitud de cliente al disminuir el valor de la **HttpServerUtility.ScriptTimeout** propiedad en el servidor.  
  
## <a name="see-also"></a>Vea también  
 [Publicar servicios Web](../core/publishing-web-services.md)
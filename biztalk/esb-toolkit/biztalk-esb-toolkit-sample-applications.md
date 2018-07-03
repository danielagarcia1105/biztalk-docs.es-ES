---
title: Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk | Microsoft Docs
description: Instalar las aplicaciones de ejemplo del Kit de herramientas ESB y obtener vínculos rápidos sobre cómo se usan en BizTalk Server
caps.latest.revision: 5
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: 81f44a6a34493210b44916a8a88cc85ad693480c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975517"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a>Aplicaciones de ejemplo de Kit de herramientas de BizTalk ESB
El Kit de herramientas de Microsoft BizTalk ESB incluye varias aplicaciones de ejemplo que puede instalar y ejecutar para ver cómo las obras ESB y cómo éste usa algunas de ESB componentes de canalización. Puede adaptar y modificar el código y las técnicas usadas en los ejemplos para sus propias aplicaciones.  
  
## <a name="install-the-sample-applications"></a>Instalar las aplicaciones de ejemplo  
  
1. Cree una carpeta denominada proyectos en la raíz de la unidad C: y cree una subcarpeta denominada Microsoft.Practices.ESB dentro de esta carpeta.  
  
   > [!NOTE]
   >  En la versión actual, la instalación compatibles es para que los archivos que residen en la carpeta C:\Projects\Microsoft.Practices.ESB. Los archivos de enlace de BizTalk que se suministran con los ejemplos dependen de esta ruta de acceso.  
  
2. Al instalar el [Kit de herramientas ESB](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), incluye un archivo .zip denominado ESBSource.zip en la ubicación de instalación especificada (de forma predeterminada, C:\Program Files\Microsoft BizTalk ESB Toolkit). Descomprima el archivo ESBSource.zip en la carpeta C:\Projects\Microsoft.Practices.ESB. Esto crea carpetas denominadas **claves** y **origen** que contiene la clave de ejemplo y los ejemplos de código fuente. La carpeta de origen contiene el código fuente de la aplicación de ejemplo y la carpeta de claves contiene las claves públicas usadas para firmar los ensamblados en las aplicaciones de ejemplo.  
  
3. Antes de ejecutar los ejemplos, quite el atributo de solo lectura en la carpeta C:\Projects\Microsoft.Practices.ESB\ para que los ejemplos se instalan correctamente.  
  
4. Si no ha usado los scripts de PowerShell antes, debe abrir PowerShell como administrador y ejecute el siguiente comando:  
  
   ```  
   set-executionpolicy unrestricted  
   ```  
  
   > [!NOTE]
   >  Para obtener más información acerca de PowerShell, consulte el [Blog de Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) y [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([ http://go.microsoft.com/fwlink/?LinkId=187594 ](http://go.microsoft.com/fwlink/?LinkId=187594)) en MSDN.  
  
5. Abra un símbolo del sistema como administrador y ejecute el siguiente comando para asegurarse de que se registran las asignaciones de scripts de WCF:  
  
   ```  
   C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
   ```  
  
> [!NOTE]
>  Deberá abrir el archivo ESBSource.zip con el fin de obtener un acceso al código de ejemplos.  

## <a name="sample-applications"></a>Aplicaciones de ejemplo  
 Los temas siguientes describen las aplicaciones de ejemplo e incluyan instrucciones de instalación adicionales en su caso:  
  
-   [Instalación de los ejemplos de administración de excepciones](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [Ejecución del ejemplo de controlador de excepciones personalizadas de reparación y reenvío](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [Ejecución del ejemplo de controlador de excepciones personalizadas de conservación de mensajes](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [Ejecución del ejemplo de procesamiento de ESB de enrutamiento de mensajes de error de BizTalk](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [Instalación y ejecución del ejemplo de rampa de itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [Instalación y ejecución del ejemplo del componente MQRFH2 de JMS](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [Instalación y ejecución del ejemplo de componente de espacio de nombres](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [Instalación y ejecución del ejemplo de servicio de transformación](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [Instalación y ejecución del ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [Instalación y ejecución del ejemplo de operaciones de BizTalk](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [Instalación y ejecución del ejemplo de servicio de resolución](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [Instalación y ejecución del ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [Instalación y ejecución del ejemplo de enriquecimiento de mensajes](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [Instalación y ejecución del ejemplo de varios servicios web](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [Instalación y ejecución del ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [Ejecución del ejemplo de servicio de control de excepciones](../esb-toolkit/running-the-exception-handling-service-sample.md)
---
title: Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
description: "Instalar las aplicaciones de ejemplo del Kit de herramientas ESB y obtener vínculos rápidos usarlos en BizTalk Server"
caps.latest.revision: "5"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: f9d1af5c2bc8c16ec14f8e13109f0edfe13b86cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-sample-applications"></a>Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varias aplicaciones de ejemplo que se pueden instalar y ejecutar para ver cómo funciona la ESB y cómo utiliza algunas de ESB componentes de canalización. Puede adaptar y modificar el código y las técnicas que se usan en los ejemplos para sus propias aplicaciones.  
  
## <a name="install-the-sample-applications"></a>Instalar las aplicaciones de ejemplo  
  
1.  Cree una carpeta denominada proyectos en la raíz de la unidad C: y cree una subcarpeta denominada Microsoft.Practices.ESB en esta carpeta.  
  
    > [!NOTE]
    >  En la versión actual, la instalación compatible es para que los archivos que residen en la carpeta C:\Projects\Microsoft.Practices.ESB. Los archivos de enlace de BizTalk que se suministran con los ejemplos dependen de esta ruta de acceso.  
  
2.  Al instalar el [Kit de herramientas ESB](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), incluye un archivo .zip que se denomina ESBSource.zip en la ubicación de instalación especificada (de forma predeterminada, C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]). Descomprima el archivo ESBSource.zip en la carpeta C:\Projects\Microsoft.Practices.ESB. Esto crea carpetas denominadas **claves** y **origen** que contienen la clave de ejemplo y los ejemplos de código fuente. La carpeta de origen contiene el código fuente de la aplicación de ejemplo y la carpeta de claves contiene las claves públicas que se usa para firmar los ensamblados en las aplicaciones de ejemplo.  
  
3.  Antes de ejecutar los ejemplos, quite el atributo de sólo lectura en la carpeta C:\Projects\Microsoft.Practices.ESB\ para que los ejemplos se instalan correctamente.  
  
4.  Si no ha utilizado las secuencias de comandos de PowerShell antes, debe abrir PowerShell como administrador y ejecute el siguiente comando:  
  
    ```  
    set-executionpolicy unrestricted  
    ```  
  
    > [!NOTE]
    >  Para obtener más información acerca de PowerShell, vea el [Blog de Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/? LinkId = 187593](http://go.microsoft.com/fwlink/?LinkId=187593)) y [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/? LinkId = 187594](http://go.microsoft.com/fwlink/?LinkId=187594)) en MSDN.  
  
5.  Abra un símbolo del sistema como administrador y ejecute el siguiente comando para asegurarse de que se registran los mapas de secuencia de comandos WCF:  
  
    ```  
    C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
    ```  
  
> [!NOTE]
>  Deberá abrir el archivo ESBSource.zip con el fin de obtener acceso al código de ejemplos.  

## <a name="sample-applications"></a>Aplicaciones de ejemplo  
 Los temas siguientes describen las aplicaciones de ejemplo e incluyen instrucciones de instalación adicionales si procede:  
  
-   [Instalar los ejemplos de administración de excepciones](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [Ejecutar el ejemplo de controlador de excepciones personalizadas de reparación y vuelva a intentarlo](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [Ejecuta el mensaje conservar ejemplo del controlador de excepciones personalizadas](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [Ejecución de BizTalk no pudo ejemplo de procesamiento de ESB de enrutamiento de mensajes](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [Instalar y ejecutar el ejemplo en rampa itinerario](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [Instalar y ejecutar el ejemplo del componente MQRFH2 JMS](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [Instalar y ejecutar el ejemplo del componente de Namespace](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de servicio de transformación](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de operaciones de BizTalk](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de servicio de resolución](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de dispersión y recopilación](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de enriquecimiento de mensajes](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [Instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [Ejecutar el ejemplo de servicio de control de excepciones](../esb-toolkit/running-the-exception-handling-service-sample.md)
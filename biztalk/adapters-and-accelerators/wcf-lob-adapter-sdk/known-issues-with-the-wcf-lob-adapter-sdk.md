---
title: Problemas conocidos con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2cda4248-2efa-4e3d-a5ce-9a57728c51e1
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 090c53b91ad30f522bc5522fbeb457d7de868456
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-wcf-lob-adapter-sdk"></a>Problemas conocidos relacionados con el SDK de adaptador LOB de WCF
En este tema se describe problemas conocidos asociados a la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. También proporciona soluciones para algunos de estos problemas.  
  
## <a name="unable-to-change-sdk-features-using-add-or-remove-programs"></a>No se puede cambiar características del SDK mediante Agregar o quitar programas
 **Problema**: mediante **agregar o quitar programas** en el Panel de Control no se puede cambiar las características de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en un equipo que ejecute Windows Vista.  
  
 **Resolución**: en lugar de usar **agregar o quitar programas** para modificar la instalación, vuelva a ejecutar el programa Setup.exe.  
  
## <a name="base-runtime"></a>Base de tiempo de ejecución  
  
### <a name="applications-using-transactions-in-asynchronous-proxy-must-explicitly-call-proxyopen"></a>Las aplicaciones que usan transacciones en Proxy asincrónico deben llamar explícitamente a Proxy.Open  
 **Problema**: las aplicaciones que utilizan las transacciones con un adaptador en un proxy asincrónico deben llamar explícitamente a proxy. Abrir para las transacciones de flujo.  
  
 **Resolución**: Esto puede hacerse una vez que el proxy generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] en el programa cliente, como se muestra:  
  
```  
EchoAdapterClient echoAdapterProxy = new EchoAdapterClient("mEchoConfiguration");  
echoAdapterProxy.Open();  
...  
```  
  
### <a name="iduplexchannel-shape-not-supported"></a>Forma de IDuplexChannel no compatible  
 **Problema**: IDuplexChannel la forma del canal no se admite en esta versión.  
  
 **Resolución**: usar el modelo de canal de WCF para crear un enlace personalizado de WCF que admite canales dúplex.  
  
### <a name="request-schema-generated-with-or-without-in-or-out-parameters"></a>Esquema de solicitud generado con o sin en o los parámetros de salida  
 **Problema**: en el **ExportInputXmlSchema** método de la clase **OperationMetadata**, siempre se genera el esquema de solicitud, aunque no puede contener ninguno de o los parámetros de salida.  
  
### <a name="providing-multiple-operation-namespaces"></a>Proporciona varios espacios de nombres de operación  
 **Problema**: si el desarrollador de adaptadores proporciona varios espacios de nombres de operación para el grupo de una operación, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] genera un WSDL no válido. La entrada generada y la parte de mensaje de salida para cada operación no se vinculará a la referencia de esquema correcto.  
  
 **Resolución**: asegúrese de que cada OperationMetadata.OperationGroup está asignada a un único OperationMetadata.OperationNamespace.  
  
### <a name="overloaded-operations-not-supported"></a>Sobrecargado las operaciones no admitidas  
 **Problema**: en esta versión, el componente del generador de contrato dinámica (generador de WSDL) del SDK no admite operaciones con sobrecarga, es decir, las operaciones con el mismo nombre pero con distintos firma.  
  
### <a name="fault-contract-not-supported"></a>No admitido el contrato de error  
 **Problema**: en esta versión, el componente del generador de contrato dinámica (generador de WSDL) del SDK no admite metadatos del contrato de error.  
  
### <a name="failure-when-receiving-messages"></a>Error al recibir mensajes  
 **Problema**: cuando se reciben, hay una posibilidad de que el adaptador de un error al procesar determinados mensajes si el **tiempo de espera de recepción** enlaza la propiedad se establece en un valor pequeño. El error devuelto será específico para el adaptador.  
  
 **Solución alternativa**: establecer el **tiempo de espera de recepción** propiedad de enlace en un valor grande, por ejemplo 23:59:59, que es el valor máximo.  
  
### <a name="adapter-stalls-during-message-processing"></a>Adaptador se detiene temporalmente durante el procesamiento de mensajes  
 **Problema**: si hay un gran número de solicitudes para el adaptador, el procesamiento de los elementos de trabajo puede parecer que se detienen.  
  
 Cuando se abre una nueva conexión, el adaptador se pone en cola con un elemento de trabajo que se procesarán mediante el grupo de subprocesos. NET. Una vez que se abre una conexión, aún más los elementos de trabajo se ponen en cola para procesar cada mensaje. Si se ha agotado el grupo de subprocesos, puede producirse un interbloqueo donde las solicitudes para abrir nuevas conexiones bloquean las solicitudes para procesar los mensajes.  
  
 **Resolución**: finalmente las solicitudes agotará el tiempo y el procesamiento continuará, sin embargo, la solución recomendada es o reducir el número de mensajes que pueden procesar o aumentar el número de subprocesos en el grupo de subprocesos.  
  
 Para aumentar el número de subprocesos, modifique el valor de [ProcessModelSection.MaxWorkerThreads propiedad](https://msdn.microsoft.com/library/system.web.configuration.processmodelsection.maxworkerthreads.aspx).  
  
## <a name="design-time-proxy-and-schema-generation-tools"></a>Proxy de tiempo de diseño y herramientas de generación de esquema  
  
### <a name="limitations-with-select-contract-type"></a>Limitaciones en el tipo de contrato Select  
 **Problema**: el filtrado de "tipo de contrato Select" se aplica en el árbol de categorías y la lista de operaciones disponibles. Si el consumidor de adaptador selecciona un nodo de categoría que contienen operaciones de entrada y salidas, todos ellos va a formar parte de WSDL y el proxy generado, sin tener en cuenta el filtrado de "tipo de contrato Select".  
  
 **Resolución**: seleccione las operaciones individuales en lugar de seleccionar la categoría por completo.  
  
### <a name="error-with-add-adapter-service-reference-visual-studio-plug-in"></a>Error con agregar adaptador servicio referencia complemento de Visual Studio  
 **Problema**: en BizTalk un proyecto en Visual Studio, si un servidor proxy ya se ha generado mediante el uso de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], generar otro proxy desde el mismo adaptador generará este error: "el espacio de nombres '\<espacio de nombres global >' ya contiene una definición para '{nombre del contrato}' al compilar el proyecto. "  
  
 Esta versión no permite la edición del proxy.  
  
 **Resolución**: quitar los archivos de proxy extraños en el proyecto de BizTalk. Si las operaciones adicionales deben incluirse en el proxy generado, elimine el archivo de proxy y usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar o examinar los metadatos y volver a generar el proxy.  
  
### <a name="error-with-consume-adapter-service-biztalk-project-add-in"></a>Error con Consume Adapter Service complemento del proyecto de BizTalk  
 **Problema**: como se muestra en el problema anterior, en BizTalk proyecto en Visual Studio, si existen tipos comunes en los esquemas generados a partir de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], no se puede compilar el proyecto de BizTalk.  
  
 **Resolución**: quitar los archivos de esquema XML extraños en el proyecto de BizTalk, use la referencia de servicio de adaptador para buscar o examinar los metadatos necesarios y volver a generar los nuevos archivos de esquema XML.  
  
### <a name="error-with-rootnode-typename-in-biztalk-projects"></a>Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**: en BizTalk un proyecto en Visual Studio, si los esquemas generan a partir del [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] contienen caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el error siguiente en tiempo de compilación: "nodo \<referencia de nodo >-especifique un nombre de tipo .NET válido para este nodo raíz.  El nombre de tipo .NET actual de este nodo raíz no es válido (es una palabra reservada de BizTalk o un identificador no válido de C#).  
  
 **Resolución**: seleccione el nodo raíz al que hace referencia en el error y, en Propiedades, quite los caracteres no válidos o palabras reservadas de la **RootNode TypeName** propiedad.  
  
### <a name="metadata-generation-tool-limitations"></a>Limitaciones de herramienta de generación de metadatos  
 **Problema**: si el desarrollador de adaptadores proporciona una estructura de esquema XML en un OperationMetadata y/o TypeMetadata clase derivada, y el esquema XML contiene construcciones que se deben omitir o se prohíbe por DataContractSerializer, los metadatos herramienta de generación de vuelve a utilizar la clase XmlSerializer para la serialización.  
  
 **Resolución**: quite las construcciones prohibidas en el esquema, o use el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] modelo de objetos de metadatos para generar las definiciones de esquema XML que cumplen con DataContractSerializer.  
  
### <a name="binding-name-property-does-not-take-effect"></a>Propiedad de nombre de enlace no tiene ningún efecto  
 **Problema**: cambiar la propiedad de nombre de enlace en el **General de propiedades de enlace** pestaña de la **Agregar referencia de servicio de adaptador** cuadro de diálogo no surtan efecto.  
  
 **Resolución**: Use la AdapterBinding clase derivada para cambiar el nombre como sigue:  
  
```  
[Browsable(false)]  
public new virtual string Name  
{  
     set  
     {  
          base.Name = value;  
     }  
     get  
     {  
          return base.Name;  
     }  
}  
```  
  
### <a name="timeout-when-retrieving-metadata"></a>Tiempo de espera al recuperar los metadatos  
 **Problema**: si el adaptador contiene muchas operaciones, se puede producir un tiempo de espera al recuperar metadatos mediante herramientas como el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], Asistente para la desarrollo del servicio del adaptador de WCF, o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] si se intenta recuperar muchas operaciones en una vez.  
  
 **Resolución**: reduzca el número de operaciones seleccionadas.  
  
### <a name="avoid-generating-schemas-which-reference-an-external-import"></a>Evitar la generación de esquemas, que hacen referencia a una importación externa  
 **Problema**: no se deben generar esquemas que contienen una o varias referencias a las importaciones externas. Si es así, no seguir los vínculos externos.  
  
## <a name="setup"></a>ssNoVersion  
  
### <a name="setup-halts-while-checking-disk-space"></a>El programa de instalación se detiene al comprobar el espacio en disco  
 **Problema**: al instalar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], es posible que reciba un cuadro de diálogo que indica que el programa de instalación comprueba si hay espacio disponible en disco y el programa de instalación no continuará.  
  
 **Resolución**: cuando se produce este problema, puede solucionar este problema mediante la realización de una instalación silenciosa de [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en un símbolo del sistema. Por ejemplo:  
  
```  
Msiexec.exe /package AdapterFramework.msi /qr  
```  
  
### <a name="biztalk-server-developer-tools-required"></a>Herramientas de desarrollo de BizTalk Server necesarios  
 **Problema**: cuando el sistema de destino tiene Visual Studio y Microsoft BizTalk Server sin herramientas de desarrollador, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se producirá un error en el programa de instalación. Esto es porque requiere herramientas de desarrollo de BizTalk Server esté presente en el equipo para poder instalar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
 **Resolución**: asegúrese de que el equipo de destino tiene BizTalk Server instalado con herramientas de desarrollo antes de instalar la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
### <a name="corrupt-biztalk-server-installation-causes-sdk-to-fail"></a>Causas de instalación de BizTalk Server SDK para errores esté dañado  
 **Problema**: una instalación dañada de BizTalk Server puede provocar la instalación del SDK producir el error siguiente: "DirectoryNotFound exception".  
  
 **Resolución**: desinstalar y reinstalar el servidor BizTalk Server.  
  
 
## <a name="see-also"></a>Vea también  
 [Introducción a BizTalk Server](../../core/getting-started-with-biztalk-server.md)
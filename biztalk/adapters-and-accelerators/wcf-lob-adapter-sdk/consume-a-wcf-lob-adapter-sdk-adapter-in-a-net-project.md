---
title: Utilizar un adaptador de SDK de adaptador LOB de WCF en un proyecto .NET | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6934b96d-5704-4f3c-b53f-4e36e352a338
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622c6ad687e681591071d472e2ff8a9e8c515f95
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-net-project"></a>Utilizar un adaptador de SDK de adaptador LOB de WCF en un proyecto de .NET
Para consumir un adaptador que se generan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe agregar una referencia de servicio al proyecto. Puede hacerlo:  
  
-   Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], que se instala como parte de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
-   Uso de svcutil.exe (el ServiceModel utilidad de metadatos), que se instala como parte del SDK de Windows.  
  
## <a name="add-a-service-reference-using-the-add-adapter-service-reference-plug-in"></a>Agregue una referencia de servicio mediante el complemento de agregar referencia de servicio de adaptador  
 La [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] puede usarse para examinar y buscar los metadatos y para generar clases de proxy de .NET CLR con los tipos y las operaciones seleccionadas.  
  
 
1.  Abra la aplicación de .NET en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en el **proyecto** menú y, a continuación, haga clic en **Agregar referencia de servicio de adaptador**.  
  
    > [!NOTE]
    >  Esta opción no aparece para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos.  
  
3.  En el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] pantalla, desde el **selecciona un enlace** lista desplegable, seleccione un enlace del adaptador.  
  
4.  Para configurar el URI de conexión para el enlace del adaptador seleccionado y para proporcionar las credenciales, propiedades de URI y propiedades de enlace, haga clic en **configurar**. Los requisitos reales varían según el enlace del adaptador seleccionado.  
  
5.  Cuando se ha configurado el URI, haga clic en **Aceptar**.  
  
6.  Haga clic en **Conectar**. Si el URI de conexión es válida y se aceptan las credenciales del cliente (si existe), el **categoría** panel se debe rellenar con las categorías y las operaciones proporcionadas por el adaptador.  
  
7.  Si el adaptador es compatible con la búsqueda, se activará el campo de búsqueda. En caso contrario, puede filtrar por tipo de contrato, explorar los tipos y las operaciones haciendo clic en los nodos en el **categoría** panel.  
  
8.  Para ver opciones de generación de proxy avanzada, haga clic en **avanzadas**. Existen varias opciones:  
  
    |Opción|Opción de svcutil.exe equivalente|Description|  
    |------------|-----------------------------------|-----------------|  
    |**Generar métodos asincrónicos**|/Async|Genera firmas del método sincrónicas y asincrónicas.<br /><br /> El valor predeterminado (si no está seleccionada): genera solo firmas de método sincrónicas.|  
    |**Generar contratos de mensaje**|/messageContract|Genera tipos de contrato de mensaje.|  
    |**Haga que los tipos internos**|/ interno|Genera clases marcadas como internas.<br /><br /> El valor predeterminado (si no está seleccionada): generar clases públicas.|  
    |**Habilitar el enlace de datos**|/enableDataBinding|Implementa el System.ComponentModel.INotifyPropertyChanged interfaz en todos los tipos de contrato de datos para habilitar el enlace de datos.|  
    |**Importar tipos de datos que no sean como IXmlSerializable**|/importXmlTypes|Configura el serializador de contratos de datos para importar tipos que no sean de contratos de datos como tipos IXmlSerializable.|  
    |**Generar la interfaz de canal**||Genera la interfaz de canal.|  
    |**Marca de clases serializables**||Selecciona si desea generar los tipos de datos con un serializador.|  
    |**No generan app.config**|/noConfig|No genera el archivo de configuración de aplicación.|  
    |**Serializador**<br /><br /> **Automático**|/Serializer:auto|Selecciona automáticamente el serializador para la serialización y deseralization.|  
    |**Serializador**<br /><br /> **Serializador DataContract**|/Serializer:DataContractSerializer|Genera tipos de datos que utilizan el serializador de contratos de datos para la serialización y deserialización|  
    |**Serializador**<br /><br /> **XmlSerializer**|/ Serializer: XmlSerializer|Genera tipos de datos que utilicen XmlSerializer para la serialización y deserialización.|  
  
9. Para generar los artefactos de proxy, haga clic en **Aceptar**. El número de artefactos varía según el tipo de contrato.  
  
    |Tipo de contrato|Artefacto|Description||  
    |-------------------|--------------|-----------------|-|  
    |Salida|Proxy de WCF de CLR|Contiene la implementación del contrato y servicio.||  
    |Salida||App.config|Contiene el \<extremo\> y \<enlaces\> elementos para \<sistema. ServiceModel\>\<cliente\>.|  
    |Entrada|Interfaz de servicio WCF de CLR|Contiene el contrato.||  
    |Entrada||Implementación de servicio de WCF de CLR|Implementación de código auxiliar que se deriva el contrato.|  
    |Entrada||App.config|Contiene el \<extremo\>, \<enlaces\> y \<comportamientos\> elementos para \<sistema. ServiceModel\>\<servicio\>.|  
  
10. Ahora puede usar al proxy de la aplicación.  
  
## <a name="adding-a-service-reference-by-using-svcutilexe"></a>Agregar una referencia de servicio mediante svcutil.exe  
 Svcutil.exe es una utilidad de línea de comandos que puede utilizarse para recuperar metadatos y generar clases de proxy de .NET CLR, que, a continuación, se pueden agregar a un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto. Para obtener más información acerca de svcutil.exe, vea [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx). 
  
 Para generar una clase de proxy de un adaptador alojado en IIS  
  
1.  En el símbolo del sistema, escriba **svcutil.exe "http://localhost/adapter/AdapterService.svc?wsdl" /config:app.config**. Reemplace la ruta de acceso HTTP con la ruta de acceso correcta para el adaptador hospedado. Esto crea un archivo .cs que contiene el proxy de .NET CLR y output.config que contiene el \<enlaces\> y cliente \<extremo\> para \<system.serviceModel\>.  
  
    > [!NOTE]
    >  Si el adaptador contiene muchas operaciones, puede limitar las operaciones devueltas utilizando una cadena de consulta de ' op =' seguido por el nombre de la operación en el que esté interesado. Por ejemplo: `svcutil.exe “http://localhost/adapter/AdapterService.svc?wsdl&op=Echo/EchoString&op=Echo/EchoArray”` genera código de proxy para las operaciones EchoString y EchoArray.  
  
2.  Abra el proyecto en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
    1.  En **el Explorador de soluciones**, haga clic en el proyecto, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. En el **Agregar elemento existente** cuadro de diálogo, seleccione los archivos .cs y app.config creados anteriormente.  Haga clic en **Agregar**.  
  
    2.  En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**. En el **.NET** ficha, seleccione **System.ServiceModel**y, a continuación, haga clic en **Aceptar**. Ahora puede usar al proxy de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [Utilizar un adaptador creado mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)
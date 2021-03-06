---
title: Interfaz IStaticAdapterConfig de adaptador estático | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8d95ba4a5945cb43e3681055750cdad628759
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277388"
---
# <a name="static-adapter-istaticadapterconfig-interface"></a>IStaticAdapterConfig de adaptador estático (interfaz)
Un adaptador estático de tiempo de diseño debe implementar la **IStaticAdapterConfig** interfaz. Esto le permite interactuar con el Asistente para agregar metadatos de adaptador y obtener del adaptador organizaciones de servicios y descripciones de servicio individual. Las llamadas del Asistente para la **GetServiceOrganization** y **GetServiceDescription** métodos para extraer información de metadatos con el que el adaptador interactúa y agregarla a un BizTalk project en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 El **GetServiceOrganization** método obtiene un documento de instancia XML que representa la organización jerárquica de servicios expuestos del adaptador. Esta estructura genera el árbol de organización de servicio que se ve en el **seleccionar servicios para importar** página del Asistente para agregar metadatos de adaptador.  
  
 Después de seleccionar los servicios que se va a importar, el asistente llama a la **GetServiceDescription** método para obtener una matriz de archivos de lenguaje de descripción de servicios Web (WSDL) correspondientes a las categorías de servicio que se seleccionaron en el complemento Árbol de Asistente de metadatos de adaptador. Los esquemas que representan los servicios se generan como archivos XSD y se agregan a su proyecto de BizTalk después de completar el Asistente para agregar metadatos de adaptador.  
  
 En el ejemplo de adaptador de archivo, el **GetServiceOrganization** y **GetServiceDescription** métodos residen en el **StaticAdapterManagement** clase en el Del archivo de clase. Las llamadas del Asistente para la **GetServiceOrganization** método para obtener la estructura de árbol para mostrar en el **seleccionar servicios para importar** página. En **GetServicesOrganization** el codificado de forma rígida obtener valor del archivo AdapterManagement.CategorySchema.xml se usa tal como se muestra en el siguiente fragmento de código. Como programador de adaptadores, necesitará agregar la lógica para devolver el archivo XML adecuado.  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  No olvide modificar el **GetServiceDescription** método de la **StaticAdapterManagement** (clase) y no de la **DynamicAdapterManagement** (clase), que aparece en primer lugar en el archivo.  
  
 El código siguiente procede del **GetServiceDescription** método del archivo AdapterManagement.cs. El archivo service1.wsdl está codificado de forma rígida como el archivo devuelto WSDL. Devuelve esquemas representados como archivos WSDL. El `wsdls` parámetro es una matriz de referencias únicas WSDL correspondientes a las referencias WSDL en el código fuente XML cargado por **GetServicesOrganization**. El conjunto devuelto de descripciones WSDL se utiliza para generar los tipos de puerto y los tipos de mensaje para el proyecto de BizTalk. Si tiene más de un tipo de esquema disponible para la selección en el árbol, necesitará más de un archivo WSDL. Si tiene varias opciones WSDL y esquemas posibles, quizás desee agregar una búsqueda en base de datos para devolver el archivo correcto WSDL.  
  
```  
/// <summary>     
        /// Get the WSDL file name for the selected WSDL  
        /// </summary>  
        /// <param name="wsdls">place holder</param>  
        /// <returns>An empty string[]</returns>  
        public string[] GetServiceDescription(string[] wsdls)   
      {  
            string[] result = new string[1];  
            result[0] = GetResource("AdapterManagement.service1.wsdl");  
            return result;  
        }  
```  
  
## <a name="see-also"></a>Vea también  
 [Configuración estática de adaptador en tiempo de diseño](../core/static-design-time-adapter-configuration.md)
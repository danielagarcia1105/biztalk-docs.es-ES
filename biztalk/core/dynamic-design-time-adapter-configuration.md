---
title: "Configuración de adaptador en tiempo de diseño dinámico | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36127d62-0348-42bb-981f-19fcad26efce
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de12e705c725c4b8e72cf4b6ffbd4cdf1d939265
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-design-time-adapter-configuration"></a>Configuración dinámica de adaptador en tiempo de diseño
Hay situaciones en las que la configuración estática de adaptador en tiempo de diseño y la interfaz de usuario predeterminada estándar en el Asistente para agregar metadatos de adaptador no presentan la suficiente flexibilidad para mostrar los servicios de un adaptador para un proyecto de BizTalk que se va a importar. De forma alternativa, puede usar la configuración dinámica en tiempo de diseño en la que proporcione una interfaz de usuario (IU) personalizada para que el asistente muestre y seleccione los servicios del adaptador. El marco de trabajo de adaptadores de BizTalk proporcione un conjunto de API que puede usar para importar los esquemas necesarios para el adaptador y para que se muestre la interfaz de usuario personalizada.  
  
 En esta sección se explica cómo se implementa la función de configuración dinámica en tiempo de diseño para el adaptador personalizado. Los cambios que decida hacer se basarán en las necesidades de las aplicaciones con las que el adaptador se comunica y la lógica que el adaptador necesita implementar. Vínculos a secciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se proporciona ayuda que describe estos pasos con más detalle o proporciona información adicional cuando esté disponible. Además, resalta los lugares de la documentación del adaptador de archivo de ejemplo donde hay ejemplos relevantes.  
  
## <a name="guidelines-for-the-dynamic-development-process"></a>Directrices del proceso de desarrollo dinámico  
 La lista siguiente contiene recomendaciones para generar la funcionalidad dinámica en tiempo de diseño en el adaptador. Durante el desarrollo no debe realizar todos estos pasos ni seguirlos en un orden estricto.  
  
1.  Cree una lista de los requisitos de configuración del adaptador y de los parámetros de configuración que necesite definir. Si los parámetros se usan de forma global para todas las ubicaciones de recepción y puertos de envío, especifíquelos en el archivo de configuración de esquema del controlador. Si son específicos del puerto o la ubicación, configúrelos en los archivos de configuración del puerto de envío y de la ubicación de recepción.  
  
2.  Modifique las páginas de propiedades del adaptador par registrar los parámetros de configuración nuevos. Para obtener información acerca de este paso, consulte [esquemas de configuración de adaptador](../core/adapter-configuration-schemas.md).  
  
3.  Cree una interfaz de usuario (IU) personalizada para que el Asistente para agregar metadatos de adaptador seleccione el esquema que va a agregar al proyecto. Ésta es la única recomendación, de las enumeradas, que marca la diferencia entre un adaptador dinámico y uno estático. Para obtener más información acerca de este paso, consulte [método DisplayUI de adaptador dinámico](../core/dynamic-adapter-displayui-method.md) y la clase [Microsoft.BizTalk.Adapter.Framework.IDynamicAdapterConfig.DisplayUI](http://msdn.microsoft.com/library/microsoft.biztalk.adapter.framework.idynamicadapterconfig.displayui.aspx).  
  
4.  Modifique el código de ejemplo para que devuelva esquemas como archivos Lenguaje de descripción de servicios web (WSDL). Para obtener más información acerca de este paso, consulte [interfaz IStaticAdapterConfig de adaptador estática](../core/static-adapter-istaticadapterconfig-interface.md).  
  
5.  Modifique los archivos de WSDL que existen o cree archivos WSDL nuevos. Para obtener más información acerca de este paso, consulte [archivos WSDL del adaptador](../core/adapter-wsdl-files.md).  
  
6.  Modifique el código de ejemplo para que devuelva archivos XSD adicionales que el adaptador necesita y que no están incluidos en los archivos WSDL. Para obtener más información acerca de este paso, consulte [método GetSchema del adaptador](../core/adapter-getschema-method.md).  
  
7.  Modifique las claves de registro del adaptador y ejecute el archivo de Registro del adaptador. Para obtener más información acerca de este paso, consulte [archivo de registro del adaptador](../core/adapter-registration-file.md).  
  
8.  Instale el adaptador estático en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información acerca de este paso, consulte [instalar el adaptador en BizTalk Server](../core/install-the-adapter-into-biztalk-server.md).  
  
9. Pruebe los cambios realizados en las páginas de propiedades del adaptador. Vuelva a generar el adaptador para probar la interfaz de usuario que aparece en el Asistente para agregar metadatos de adaptador. Para obtener más información acerca de este paso, consulte [compilar y probar el proyecto de adaptador](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Método DisplayUI de adaptador dinámico](../core/dynamic-adapter-displayui-method.md)
---
title: Exponer la configuración de adaptador como una propiedad de enlace mediante el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59728113-917e-4bca-8e1a-609cd6558944
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a51833c9f1a27185654bf8f0ddaca0fdd8ac0b57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002341"
---
# <a name="expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk"></a>Exponer la configuración de adaptador como una propiedad de enlace mediante el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] usa las propiedades definidas en clases diferentes para configurar el grupo de conexiones, memoria caché de metadatos y otros comportamientos de adaptador. Este tema describe cómo puede exponer estas propiedades como propiedades de enlace, por lo que el consumidor del adaptador puede establecer a través de un archivo de configuración.  
  
### <a name="to-surface-an-adapter-setting-as-an-adapter-binding-property"></a>Para mostrar una configuración de adaptador como una propiedad de enlace del adaptador  
  
1. Inicie Visual Studio y, a continuación, en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2. Elija la **adaptador LOB de WCF** plantilla y, a continuación, proporcione el resto de información de proyecto de adaptador.  
  
3. Recorrer paso a paso el [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]. Cuando llegue a la **propiedades del adaptador** página, agregue las propiedades de enlace que desea exponer proporcionando un **nombre de la propiedad**, **tipo de datos**, y  **Valor predeterminado**y, a continuación, haga clic en **agregar** para agregar la nueva propiedad de adaptador.  
  
4. Completar la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]. El proyecto debe contener nuevos archivos proporcionados por el asistente.  
  
5. En Visual Studio, en el Explorador de soluciones, abra la clase derivada de adaptador. Por ejemplo, si el nombre del proyecto de adaptador es "SampleAdapter", la clase de adaptador derivada puede encontrarse en "SampleAdapter.cs".  
  
6. Quite las variables privadas para las propiedades que se desean obtener y establecer de la configuración del adaptador. Las variables privadas generadas por el [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)].  
  
7. Actualizar los métodos get/set para la configuración del adaptador desde y hacia los valores de lectura/escritura. En el ejemplo siguiente se usa una propiedad del adaptador para permitir la habilitación de contadores de rendimiento.  
  
   ```  
   [System.Configuration.ConfigurationProperty("enablePerfCounters", DefaultValue = false)]  
   public bool EnablePerfCounters  
   {  
       get { return environmentSettings.PerformanceCounters.Enabled;    }  
       set { environmentSettings.PerformanceCounters.Enabled = value; }  
   }  
   ```  
  
8. En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) [las actividades de desarrollo](../../esb-toolkit/development-activities.md)
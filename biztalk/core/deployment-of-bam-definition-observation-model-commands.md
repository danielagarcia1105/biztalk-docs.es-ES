---
title: "Implementación de comandos (modelo de observación) de definición de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dba1e1a4f54b3b33ebca8297cfe9beef7c4f868
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a>Comandos de implementación de definición de BAM (modelo de observación)
Los comandos de implementación de la utilidad de administración de BAM le permiten aplicar, modificar y quitar definiciones.  
  
-   implementar-all: implementa una definición de BAM.  
  
-   Update-all: actualiza una definición de BAM.  
  
-   Remove-all: quita una definición de BAM.  
  
-   Update-livedataworkbook: actualiza la información de conexión de base de datos en un libro de datos en directo.  
  
-   Regenerate-livedataworkbook: vuelve a generar el libro de datos activos en el servidor.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="deploy-all-command"></a>Comando deploy-all  
 **Uso**  
  
 **bm.exe implementar-all - DefinitionFile:\<archivo def\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|DefinitionFile:\<archivo def\>|Ruta y nombre del archivo que contiene las definiciones que se van a implementar.|  
|Servidor:\<server\>|Opcional: El nombre del servidor que se va a implementar las definiciones. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a implementar las definiciones. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Implementa todos los artefactos desde el archivo XML especificado de definición de BAM al servidor y a la base de datos especificados. El archivo puede ser un archivo de texto que contenga el XML de definición de BAM o un libro de Excel de BAM. El archivo de definición debe incluir sólo artefactos nuevos. Si el archivo contiene artefactos que ya se han implementado, la implementación no funcionará e informará de un error.  
  
 **Consideraciones para implementar las definiciones de BAM**  
  
 Cuando implementa suscripciones de alerta, los Id. de usuario de los suscriptores se deben especificar en formato dominio\usuario.  
  
 El servicio de coordinador de transacción distribuida debe ejecutarse en el equipo en el que el **all implementar** se emite el comando.  
  
 Cuando implementa una definición, la utilidad de administración de BAM sólo admite 14 niveles de dimensión en la vista Agregación en tiempo real (ATR). Implementar niveles adicionales da genera errores de implementación.  
  
 Si define varias vistas que utilizan diferentes configuraciones de idioma e implementan su solución en un servidor que utiliza un lenguaje único, las vistas no se podrán implementar. Este escenario sólo se admite en caso de que no tenga agregaciones programadas que requieran OLAP como parte de la definición de BAM.  
  
 La utilidad de administración de BAM le limita a 49 vistas de actividad implementada cuando se habilitan las alertas BAM. El número de vistas de actividad se calcula como el sumatorio de 1 a N de la vista (n) multiplicado por el número de actividades primarias.  Por ejemplo, si implementa una vista que se esté basada en dos actividades, obtiene dos vistas de actividad.  Si implementa dos vistas, una que abarque dos actividades y otra que esté basada en una actividad única, tiene 3 vistas de actividad.  
  
 La utilidad de administración de BAM bloquea la implementación de las definiciones de BAM, que tienen varios informes de tabla dinámica que se definen en la misma combinación de nombre del cubo y de ATR. Bm.exe finalizará la implementación y mostrará el error siguiente:  
  
 Implementando vista... ERROR: Error en la implementación de BAM.  
  
 Sólo una vista de tabla dinámica puede definirse en una ATR y un cubo dados.  
  
 La lista siguiente de nombres se reserva y generará un error al implementar la definición:  
  
-   RecordID  
  
-   ActivityID  
  
-   IsVisible  
  
-   IsComplete  
  
-   LastModified  
  
> [!NOTE]
>  Si bm.exe encuentra un error durante la implementación, la implementación finaliza y se deshacen los cambios en las vistas y en las actividades. Los cambios a cubo OLAP no se deshacen ya que OLAP no admite implementación transaccional.  
  
> [!NOTE]
>  Las definiciones de BAM creadas en un equipo que utiliza una configuración regional no se pueden implementar en un equipo configurado con una configuración regional diferente. Por ejemplo, una definición de BAM generada con una versión de idioma inglés de Microsoft Excel en un equipo configurado con una configuración regional en inglés no se puede implementar en un equipo configurado en japonés que utiliza la configuración regional en japonés.  
  
 **Ejemplos**  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a>Comando update-all  
 **Uso**  
  
 **bm.exe update-all - DefinitionFile:\<archivo def\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|DefinitionFile:\<archivo def\>|Ruta y nombre del archivo que contiene las definiciones desde el que se va a realizar la actualización.|  
|Servidor:\<server\>|Opcional: El nombre del servidor que se va a implementar las actualizaciones de definiciones. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos que se va a implementar las actualizaciones de definiciones. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Actualiza ciertos artefactos del XML de definición de BAM. El archivo puede ser un archivo de texto que contenga el XML de definición de BAM o un libro de Excel de BAM. La actualización no elimina artefactos que no se describen en el archivo actual de definición. Puede agregar puntos nuevos de comprobación a actividades, pero no puede quitar puntos de control de actividades implementadas. La actualización no puede ni cambiar el nombre de los puntos de control ni modificar sus propiedades.  
  
 Una vez implementada una actividad, las acciones que puede realizar sobre ella están restringidas. Específicamente, no puede eliminar elementos de una actividad a menos que esté dispuesto a que su administrador anule la implementación de toda la actividad de BAM y sus conjuntos de vista y los vuelva a implementar. Esto puede provocar una interrupción de la visibilidad y pérdidas de datos a menos que el administrador haga una copia de seguridad de los datos y los restaure.  
  
> [!NOTE]
>  No puede usar este comando para agregar actividades nuevas a una vista existente. Para agregar una vista a una actividad, debe crear una nueva vista que incluya la actividad nueva. Puede anular la implementación de la vista antigua, pero sea consciente de que perderá su historial de datos OLAP.  
  
 **Ejemplos**  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a>comando remove-all  
 **Uso**  
  
 **bm.exe remove-all DefinitionFile:\<archivo def\> [-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|DefinitionFile:\<archivo def\>|Ruta y nombre del archivo que contiene las definiciones que se van a quitar.|  
|Servidor:\<server\>|Opcional: El nombre del servidor desde el que se quitarán las definiciones. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos desde el que se quitarán las definiciones. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Quita todos los artefactos especificados en el archivo XML de definición de BAM. El archivo puede ser un archivo de texto que contenga el XML de definición de BAM o un libro de Excel de BAM. La definición de cada artefacto debe coincidir exactamente con la definición original que se utilizó para implementación.  
  
 **Ejemplos**  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a>Comando update-livedataworkbook  
 **Uso**  
  
 **bm.exe update-livedataworkbook-nombre:\<nombre de archivo de libro de trabajo de datos dinámicos\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Nombre:\<libro de trabajo de datos dinámicos\>|El nombre del libro de trabajo dinámico existente que se debe actualizar.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside el libro. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que reside el libro. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Actualiza la información de conexión de la base de datos de importación principal de BAM del libro de trabajo de datos activos de BAM especificado.  
  
> [!NOTE]
>  Al configurar una nueva cadena de conexión, debe reiniciar el servicio de TDDS para asegurarse de que éste reconoce el cambio. Para obtener más información sobre el servicio TDDS, vea [procedimientos almacenados en el servicio de Bus de eventos BAM](../core/bam-event-bus-service-stored-procedures.md).  
  
 **Ejemplos**  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a>Comando regenerate-livedataworkbook  
 **Uso**  
  
 **bm.exe regenerate-livedataworkbook - WorkbookName:\<nombre de archivo de libro de trabajo de datos dinámicos\>[-Server:\<server\> ] [-base de datos:\<base de datos\> ]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|WorkbookName:\<nombre de archivo de libro de trabajo de datos dinámicos\>|Nombre del libro de trabajo que se va a actualizar.|  
|Servidor:\<server\>|Opcional: El nombre del servidor en el que reside el libro. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos\>|Opcional: El nombre de la base de datos en el que reside el libro. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Genera un libro de trabajo de datos activos de BAM, pero no implementa el libro de trabajo.  
  
 Ejemplos  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)
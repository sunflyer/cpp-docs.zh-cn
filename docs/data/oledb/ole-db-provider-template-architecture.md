---
title: OLE DB 提供程序模板体系结构
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 099c29e141d721645c416e60be240c22d22cd869
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175634"
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB 提供程序模板体系结构

## <a name="data-sources-and-sessions"></a>数据源和会话

OLE DB 提供程序体系结构包括数据源对象和一个或多个会话。 数据源对象是每个提供程序必须实例化的初始对象。 当使用者应用程序需要数据时，它共同创建要启动该提供程序的数据源对象。 数据源对象创建一个会话对象 (使用`IDBCreateSession`接口) 通过它使用者连接到数据源对象。 ODBC 程序员可以将数据源对象视为等效于`HENV`和会话对象等效于`HDBC`。

![提供程序体系结构](../../data/oledb/media/vc4twb1.gif "提供程序体系结构")

与创建的源文件一起**OLE DB 提供程序向导**，OLE DB 模板实现数据源对象。 会话是一个对象，对应于 OLE DB `TSession`。

## <a name="mandatory-and-optional-interfaces"></a>必需和可选接口

OLE DB 提供程序模板提供预打包实现所有所需的接口。 通过 OLE DB for 多种类型的对象定义必需和可选接口：

- [数据源](../../data/oledb/data-source-object-interfaces.md)

- [会话](../../data/oledb/session-object-interfaces.md)

- [Rowset](../../data/oledb/rowset-object-interfaces.md)

- [命令](../../data/oledb/command-object-interfaces.md)

- [事务](../../data/oledb/transaction-object-interfaces.md)

OLE DB 提供程序模板不会实现的行和存储对象。

下表列出了必需和可选接口，上面列出的对象根据[OLE DB 2.6 SDK 文档](https://docs.microsoft.com/previous-versions/windows/desktop/ms722784(v=vs.85))。

|组件|接口|注释|
|---------------|---------------|-------------|
|[数据源](../../data/oledb/data-source-object-interfaces.md)([CDataSource](../../data/oledb/cdatasource-class.md))|[必需] `IDBCreateSession`<br /><br /> [必需] `IDBInitialize`<br /><br /> [必需] `IDBProperties`<br /><br /> [必需] `IPersist`<br /><br /> [可选] `IConnectionPointContainer`<br /><br /> [可选] `IDBAsynchStatus`<br /><br /> [可选] `IDBDataSourceAdmin`<br /><br /> [可选] `IDBInfo`<br /><br /> [可选] `IPersistFile`<br /><br /> [可选] `ISupportErrorInfo`|与提供程序从使用者连接。 该对象用于指定用户 ID、 密码和数据源名称等连接上的属性。 该对象还可以用来管理数据源 （创建、 更新、 删除表，等）。|
|[会话](../../data/oledb/session-object-interfaces.md)([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[必需] `IGetDataSource`<br /><br /> [必需] `IOpenRowset`<br /><br /> [必需] `ISessionProperties`<br /><br /> [可选] `IAlterIndex`<br /><br /> [可选] `IAlterTable`<br /><br /> [可选] `IBindResource`<br /><br /> [可选] `ICreateRow`<br /><br /> [可选] `IDBCreateCommand`<br /><br /> [可选] `IDBSchemaRowset`<br /><br /> [可选] `IIndexDefinition`<br /><br /> [可选] `ISupportErrorInfo`<br /><br /> [可选] `ITableCreation`<br /><br /> [可选] `ITableDefinition`<br /><br /> [可选] `ITableDefinitionWithConstraints`<br /><br /> [可选] `ITransaction`<br /><br /> [可选] `ITransactionJoin`<br /><br /> [可选] `ITransactionLocal`<br /><br /> [可选] `ITransactionObject`|会话对象是使用者和提供程序之间的单个对话。 它是类似于 ODBC `HSTMT` ，可以有多个同时会话活动。<br /><br /> 会话对象是主链接以获取对 OLE DB 功能。 若要进入命令、 事务或行集对象，则翻会话对象。|
|[行集](../../data/oledb/rowset-object-interfaces.md)([CRowset](../../data/oledb/crowset-class.md))|[必需] `IAccessor`<br /><br /> [必需] `IColumnsInfo`<br /><br /> [必需] `IConvertType`<br /><br /> [必需] `IRowset`<br /><br /> [必需] `IRowsetInfo`<br /><br /> [可选] `IChapteredRowset`<br /><br /> [可选] `IColumnsInfo2`<br /><br /> [可选] `IColumnsRowset`<br /><br /> [可选] `IConnectionPointContainer`<br /><br /> [可选] `IDBAsynchStatus`<br /><br /> [可选] `IGetRow`<br /><br /> [可选] `IRowsetChange`<br /><br /> [可选] `IRowsetChapterMember`<br /><br /> [可选] `IRowsetCurrentIndex`<br /><br /> [可选] `IRowsetFind`<br /><br /> [可选] `IRowsetIdentity`<br /><br /> [可选] `IRowsetIndex`<br /><br /> [可选] `IRowsetLocate`<br /><br /> [可选] `IRowsetRefresh`<br /><br /> [可选] `IRowsetScroll`<br /><br /> [可选] `IRowsetUpdate`<br /><br /> [可选] `IRowsetView`<br /><br /> [可选] `ISupportErrorInfo`<br /><br /> [可选] `IRowsetBookmark`|行集对象是从数据源的数据。 该对象用于该数据和对数据的任何基本操作 （更新、 fetch、 移动和其他人） 的绑定。 始终具有一个行集对象来保留和处理数据。|
|[命令](../../data/oledb/command-object-interfaces.md)([CCommand](ccommand-class.md))|[必需] `IAccessor`<br /><br /> [必需] `IColumnsInfo`<br /><br /> [必需] `ICommand`<br /><br /> [必需] `ICommandProperties`<br /><br /> [必需] `ICommandText`<br /><br /> [必需] `IConvertType`<br /><br /> [可选] `IColumnsRowset`<br /><br /> [可选] `ICommandPersist`<br /><br /> [可选] `ICommandPrepare`<br /><br /> [可选] `ICommandWithParameters`<br /><br /> [可选] `ISupportErrorInfo`<br /><br /> [可选] `ICommandStream`|命令对象处理数据，例如查询上的操作。 它可以处理参数化或非参数化语句。<br /><br /> 命令对象也是负责处理参数和输出列的绑定的。 绑定是包含有关应如何检索行集中的列信息的结构。 它包含如序号、 数据类型、 长度和状态信息。|
|[事务](../../data/oledb/transaction-object-interfaces.md)（可选）|[必需] `IConnectionPointContainer`<br /><br /> [必需] `ITransaction`<br /><br /> [可选] `ISupportErrorInfo`|事务对象上的数据源定义原子工作单元，并确定每个这些工作单元之间的关系。 OLE DB 提供程序模板不直接支持此对象 （即，创建你自己的对象）。|

有关详细信息，请参阅下列主题：

- [属性映射](../../data/oledb/property-maps.md)

- [用户记录](../../data/oledb/user-record.md)

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 接口](https://docs.microsoft.com/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>

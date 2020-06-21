[chonky](../README.md) › [Globals](../globals.md) › ["components/external/FileToolbar"](_components_external_filetoolbar_.md)

# Module: "components/external/FileToolbar"

## Index

### Interfaces

* [FileToolbarProps](../interfaces/_components_external_filetoolbar_.filetoolbarprops.md)

### Variables

* [FileToolbar](_components_external_filetoolbar_.md#const-filetoolbar)

## Variables

### `Const` FileToolbar

• **FileToolbar**: *React.FC‹[FileToolbarProps](../interfaces/_components_external_filetoolbar_.filetoolbarprops.md)›* = React.memo(() => {
    const searchBarEnabled = useContext(ChonkySearchBarEnabledContext);

    const folderChainComp = useFolderChainComponent();
    const {
        buttonGroups,
        openParentFolderButtonGroup,
        searchButtonGroup,
    } = useToolbarButtonGroups();

    return (
        <div className="chonky-toolbar">
            <div className="chonky-toolbar-side chonky-toolbar-side-left">
                {openParentFolderButtonGroup && (
                    <ToolbarButtonGroup group={openParentFolderButtonGroup} />
                )}
                {folderChainComp}
            </div>
            <div className="chonky-toolbar-side chonky-toolbar-side-right">
                {buttonGroups.map((group, index) => (
                    <ToolbarButtonGroup
                        key={`button-group-${group.name ? group.name : index}`}
                        group={group}
                    />
                ))}
                {searchBarEnabled && searchButtonGroup && (
                    <ToolbarButtonGroup group={searchButtonGroup} />
                )}
            </div>
        </div>
    );
})

*Defined in [src/components/external/FileToolbar.tsx:10](https://github.com/TimboKZ/Chonky/blob/84f690f/src/components/external/FileToolbar.tsx#L10)*
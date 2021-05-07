---
title: 'StatefulButton'
type: 'component'
components:
- StatefulButton
categories:
- Buttonlike
status: 'Stable'
designStatus: 'Done'
devStatus: 'Done'
notes: ''
---

### basic usage

```jsx live
() => {
  const props = {
    labels: {
      default: 'Saved',
      pending: 'Saving',
      complete: 'Saved',
    },
    variant: 'primary',
    className: 'mr-2',
  };
  return (
    <div>
      <StatefulButton {...props} />
      <StatefulButton state="pending" {...props} />
      <StatefulButton state="complete" {...props} />
    </div>
  );
};
```

### custom icons and disable during state

```jsx live
() => {
  const downloadButtonProps = {
    labels: {
      default: 'Download',
      pending: 'Downloading',
      complete: 'Downloaded',
    },
    icons: {
      default: <Icon className="fa fa-download" />,
      pending: <Icon className="fa fa-spinner fa-spin" />,
      complete: <Icon className="fa fa-check" />,
    },
    disabledStates: ['pending'],
    variant: 'primary',
    className: 'mr-2',
  };
  return (
    <React.Fragment>
      <StatefulButton state="default" {...downloadButtonProps} />
      <StatefulButton state="pending" {...downloadButtonProps} />
      <StatefulButton state="complete" {...downloadButtonProps} />
    </React.Fragment>
  );
};
```

### custom states

```jsx live
() => {
  const buttonProps = {
    labels: {
      unedited: 'Save (no changes)',
      edited: 'Save Changes',
    },
    icons: {
      unedited: <Icon className="fa fa-save" />,
      edited: <Icon className="fa fa-save" />,
    },
    disabledStates: ['unedited'],
    variant: 'primary',
    className: 'mr-2',
  };
  return (
    <React.Fragment>
      <StatefulButton state="unedited" {...buttonProps} />
      <StatefulButton state="edited" {...buttonProps} />
    </React.Fragment>
  );
};
```
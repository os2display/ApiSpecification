# Notes

* When creating content the template selection in the request should be the basic for validation of the content field in the JSON request


Screen (egneskab region(s) templates (1:*)) -> channel(s) (1:*) -> slide(s) templates -> media (0:x)

## Templates
Screen templates
Slide tempaltes

## Refresh
Http headers last modified -> marked as dirty, service worker cache invalidated

## Data

Screen:
```json
{
  id: 'UUID',
  title: 'string',
  description: 'string',
  tags: [],
  modified: timestamp,
  created: timestamp,
  createdBy: '',
  modfiedBy: '',
  regions: [
    {
      name: "left",
      channels: [
        "uuid"
      ]
    },
    {
      name: "right",
      channels: [
        "uuid"
      ]
    }
  ],
  ?options: [''],
  ?groups: 'RBAC',
  ?activation: 'string'
}
```

Channel:
```json
{
  id: 'UUID',
  title: 'string',
  description: 'string',
  modified: timestamp,
  created: timestamp,
  createdBy: '',
  modfiedBy: '',
  tags: [],
  slides: [
    { weigth: 99, id: 'UUID', duration: 10 },
  ]
  published: {
    from: timestamp,
    to: timestamp
  }
}
```


Slide:
```json
{
  id: 'UUID',
  title: 'string',
  description: 'string',
  modified: timestamp,
  created: timestamp,
  createdBy: '',
  modfiedBy: '',
  tags: [],
  template: {
    id: 'UUID'
    options: {
      'Based on selected template',
    }
  }
  duration: ?10,
  content: {
    'based on selected template',
  },
  published: timestamp
}
```

Template: 
```json
{
  id: 'UUID',
  title: 'string',
  description: 'string',
  modified: timestamp,
  created: timestamp,
  createdBy: '',
  modfiedBy: '',
  icon: 'image',
  tags: [],
  ressource: {
    compoent: 'react js file',
    assest: [
      { type: '', url: ''}
    ],
    options: { 
      schema: 'string'
      // Options the template has - defaults
    },
    content: {
      schema: 'string',
      default: content
    }
  }
}
```

Media:
```json
{
  id: 'UUID',
  title: 'string',
  description: 'string',
  modified: timestamp,,
  created: timestamp,,
  createdBy: '',
  modfiedBy: '',
  tags: [],
  assest: [
    { type: 'image', uri: ''}
  ]
}
```



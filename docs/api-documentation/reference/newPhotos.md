---
sidebar_position: 1
---

# GET /photos

### Description
This returns a list of newly uploaded photos from Unsplash 

---

### Request

#### Query Parameters
All parameters are optional so you can call the endpoint without them
| Name      | Description                  |
|------------|------------------------------|
| `page`     | Page number (default: 1)     |
| `per-page`     | number of photos to retreive per page (default: 10)     |


#### Headers
| Key           | Value         |
|---------------|---------------|
| Authorization | Client-ID < access_key >  |

---

#### Example Response
```bash
[
  {
        "id": "ZLms1AcFjMQ",
        "slug": "a-lone-chair-sits-in-a-shallow-body-of-water-ZLms1AcFjMQ",
        "alternative_slugs": {
            "en": "a-lone-chair-sits-in-a-shallow-body-of-water-ZLms1AcFjMQ",
            "es": "una-silla-solitaria-se-encuentra-en-un-cuerpo-de-agua-poco-profundo-ZLms1AcFjMQ",
            "ja": "浅瀬の中に一人の椅子が置かれている-ZLms1AcFjMQ",
            "fr": "une-chaise-solitaire-se-trouve-dans-un-plan-deau-peu-profond-ZLms1AcFjMQ",
            "it": "una-sedia-solitaria-si-trova-in-uno-specchio-dacqua-poco-profondo-ZLms1AcFjMQ",
            "ko": "얕은-수역에-외로운-의자가-놓여-있습니다-ZLms1AcFjMQ",
            "de": "ein-einsamer-stuhl-steht-in-einem-flachen-gewasser-ZLms1AcFjMQ",
            "pt": "uma-cadeira-solitaria-fica-em-um-corpo-de-agua-raso-ZLms1AcFjMQ",
            "id": "sebuah-kursi-tunggal-duduk-di-badan-air-yang-dangkal-ZLms1AcFjMQ"
        },
        "created_at": "2025-08-17T07:58:08Z",
        "updated_at": "2025-08-25T08:48:49Z",
        "promoted_at": "2025-08-25T00:26:00Z",
        "width": 1860,
        "height": 2792,
        "color": "#8c8c8c",
        "blur_hash": "LKJtxK%Mt7oe~ooeWBj[Oaa#ayj[",
        "description": null,
        "alt_description": "A lone chair sits in a shallow body of water.",
        "breadcrumbs": [],
        "urls": {
            "raw": "https://images.unsplash.com/photo-1755417146741-8aafab9ec528?ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA&ixlib=rb-4.1.0",
            "full": "https://images.unsplash.com/photo-1755417146741-8aafab9ec528?crop=entropy&cs=srgb&fm=jpg&ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA&ixlib=rb-4.1.0&q=85",
            "regular": "https://images.unsplash.com/photo-1755417146741-8aafab9ec528?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA&ixlib=rb-4.1.0&q=80&w=1080",
            "small": "https://images.unsplash.com/photo-1755417146741-8aafab9ec528?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA&ixlib=rb-4.1.0&q=80&w=400",
            "thumb": "https://images.unsplash.com/photo-1755417146741-8aafab9ec528?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA&ixlib=rb-4.1.0&q=80&w=200",
            "small_s3": "https://s3.us-west-2.amazonaws.com/images.unsplash.com/small/photo-1755417146741-8aafab9ec528"
        },
        "links": {
            "self": "https://api.unsplash.com/photos/a-lone-chair-sits-in-a-shallow-body-of-water-ZLms1AcFjMQ",
            "html": "https://unsplash.com/photos/a-lone-chair-sits-in-a-shallow-body-of-water-ZLms1AcFjMQ",
            "download": "https://unsplash.com/photos/ZLms1AcFjMQ/download?ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA",
            "download_location": "https://api.unsplash.com/photos/ZLms1AcFjMQ/download?ixid=M3w3OTYxNjN8MHwxfGFsbHwxfHx8fHx8fHwxNzU2MTE0NjM5fA"
        },
        "likes": 70,
        "liked_by_user": false,
        "current_user_collections": [],
        "sponsorship": null,
        "topic_submissions": {
            "wallpapers": {
                "status": "approved",
                "approved_on": "2025-08-22T10:10:49Z"
            }
        },
        "asset_type": "photo",
        "user": {
            "id": "jyN_syG-ecg",
            "updated_at": "2025-08-25T08:52:02Z",
            "username": "pavlo_talpa",
            "name": "Pavlo Talpa",
            "first_name": "Pavlo",
            "last_name": "Talpa",
            "twitter_username": null,
            "portfolio_url": null,
            "bio": null,
            "location": "Ukraine",
            "links": {
                "self": "https://api.unsplash.com/users/pavlo_talpa",
                "html": "https://unsplash.com/@pavlo_talpa",
                "photos": "https://api.unsplash.com/users/pavlo_talpa/photos",
                "likes": "https://api.unsplash.com/users/pavlo_talpa/likes",
                "portfolio": "https://api.unsplash.com/users/pavlo_talpa/portfolio"
            },
            "profile_image": {
                "small": "https://images.unsplash.com/profile-1673344928632-5fa23ed8d94bimage?ixlib=rb-4.1.0&crop=faces&fit=crop&w=32&h=32",
                "medium": "https://images.unsplash.com/profile-1673344928632-5fa23ed8d94bimage?ixlib=rb-4.1.0&crop=faces&fit=crop&w=64&h=64",
                "large": "https://images.unsplash.com/profile-1673344928632-5fa23ed8d94bimage?ixlib=rb-4.1.0&crop=faces&fit=crop&w=128&h=128"
            },
            "instagram_username": "pavlo.talpa",
            "total_collections": 0,
            "total_likes": 405,
            "total_photos": 111,
            "total_promoted_photos": 23,
            "total_illustrations": 0,
            "total_promoted_illustrations": 0,
            "accepted_tos": true,
            "for_hire": true,
            "social": {
                "instagram_username": "pavlo.talpa",
                "portfolio_url": null,
                "twitter_username": null,
                "paypal_email": null
            }
        }
    },
<!-- ... more photos -->
]
```

### Error handling
401 Unauthorized → Missing or invalid token.

403 Forbidden → User doesn’t have access.

429 Too Many Requests → API rate limit exceeded.

403 - Forbidden	Missing permissions to perform request

404 - Not Found	The requested resource doesn’t exist

500, 503	Something went wrong on our end

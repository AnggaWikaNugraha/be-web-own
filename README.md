# be-web-own

### 🧑‍💼 `UserType` Interface

```typescript
export interface UserType {
  id: string;
  name: string;
  username: string;
  bio?: string;
  email?: string;
  phone?: string;
  location?: string;
  avatarUrl?: string;

  jobTitle?: string;
  company?: string;
  website?: string;

  social?: {
    github?: string;
    linkedin?: string;
    twitter?: string;
    instagram?: string;
    website?: string;
  };

  skills?: string[];
  interests?: string[];

  experience?: ExperienceType[];
  education?: EducationType[];
  certificates?: CertificateType[];

  createdAt: string;
  updatedAt?: string;
}
```

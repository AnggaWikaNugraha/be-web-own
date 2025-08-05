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

export interface ExperienceType {
  id: string;
  company: string;
  companyLogoUrl?: string;
  location?: string;
  roles: RoleType[]; // <= satu posisi pun tetap dimasukkan ke sini
}

export interface RoleType {
  id: string;
  title: string;
  employmentType: 'Fulltime' | 'Contract' | 'Internship' | 'Freelance';
  startDate: string;
  endDate?: string;
  duration?: string;
  description?: string;
  skills?: string[];
  productLink?: string;
  productTitle?: string;
}

export interface EducationType {
  id: string;
  school: string;
  degree: string; // e.g., S1, D3, etc
  fieldOfStudy: string;
  startYear: number;
  endYear?: number;
  description?: string;
}

export interface CertificateType {
  id: string;
  title: string;
  issuer: string;
  issueDate: string; // ISO
  expirationDate?: string;
  credentialUrl?: string;
}

export interface ProjectType {
  id: string;
  title: string;
  description: string;
  ownerId: string; // referensi ke user._id
  // atau ownerUsername?: string;

  role?: string;
  company?: string;
  techStack?: string[];
  year?: string;
  isPrivate?: boolean;
  demoUrl?: string;
  repoUrl?: string;
  coverImage?: string;
  createdAt: string;
  updatedAt?: string;
}

export interface FeedPostType {
  id: string;
  authorId: string;

  content: string; // teks, bisa markdown atau plain
  imageUrl?: string;
  videoUrl?: string;

  tags?: string[];

  loveCount?: number;
  commentCount?: number;
  repostCount?: number;
  shareCount?: number;

  visibility?: "public" | "connection" | "private";
  createdAt: string;
  updatedAt?: string;
}

```

```typescript

const user: UserType = {
  id: "user-001",
  name: "Angga Wika Nugraha",
  username: "anggawika",
  bio: "Frontend Developer passionate about UI/UX and scalable systems.",
  email: "angga@example.com",
  phone: "+62 812-3456-7890",
  location: "Jakarta, Indonesia",
  avatarUrl: "https://example.com/avatar.jpg",

  jobTitle: "Frontend Engineer",
  company: "PT Talenta Edukasi Sekumpul",
  website: "https://ioda.id",

  social: {
    github: "https://github.com/anggawika",
    linkedin: "https://linkedin.com/in/anggawika",
    twitter: "https://twitter.com/anggawika",
    instagram: "https://instagram.com/anggawika",
    website: "https://anggawika.dev",
  },

  skills: ["React", "TypeScript", "Tailwind CSS", "Next.js", "Node.js"],
  interests: ["Design Systems", "Open Source", "Anime"],

  experience: [
    {
      id: "exp-001",
      company: "PT Talenta Edukasi Sekumpul",
      companyLogoUrl: "https://example.com/logo-tes.png",
      location: "Jakarta",
      roles: [
        {
          id: "role-001",
          title: "Frontend Developer",
          employmentType: "Fulltime",
          startDate: "2023-01-01",
          endDate: "2024-12-31",
          duration: "2 years",
          description: "Membangun platform Ioda Academy menggunakan Next.js dan Tailwind CSS.",
          skills: ["Next.js", "React", "Tailwind"],
          productLink: "https://ioda.id",
          productTitle: "Ioda Academy"
        },
        {
          id: "role-002",
          title: "UI Engineer",
          employmentType: "Fulltime",
          startDate: "2025-01-01",
          description: "Mengembangkan UI kit dan design system untuk aplikasi internal.",
          skills: ["Figma", "Storybook"]
        }
      ]
    }
  ],

  education: [
    {
      id: "edu-001",
      school: "Universitas Indonesia",
      degree: "S1",
      fieldOfStudy: "Ilmu Komputer",
      startYear: 2018,
      endYear: 2022,
      description: "Aktif di organisasi kampus dan kompetisi programming."
    }
  ],

  certificates: [
    {
      id: "cert-001",
      title: "React Developer Certification",
      issuer: "Meta",
      issueDate: "2023-05-01",
      credentialUrl: "https://certificates.meta.com/react-developer"
    }
  ],

  createdAt: "2023-01-01T00:00:00Z",
  updatedAt: "2025-08-01T12:00:00Z"
};

const project: ProjectType = {
  id: "proj-001",
  title: "Ioda Academy Platform",
  description: "Platform pembelajaran online dengan fitur assessment dan video course.",
  ownerId: "user-001",
  role: "Frontend Lead",
  company: "PT Talenta Edukasi Sekumpul",
  techStack: ["Next.js", "Tailwind", "Node.js", "MongoDB"],
  year: "2024",
  isPrivate: false,
  demoUrl: "https://ioda.id",
  repoUrl: "https://github.com/anggawika/ioda-academy",
  coverImage: "https://example.com/project-cover.png",
  createdAt: "2024-01-01T00:00:00Z",
  updatedAt: "2024-06-01T12:00:00Z"
};

const feedPost: FeedPostType = {
  id: "post-001",
  authorId: "user-001",
  content: "Baru saja deploy v2 dari Ioda Academy 🎉 Sekarang lebih cepat dan responsif!",
  imageUrl: "https://example.com/post-image.jpg",
  tags: ["#frontend", "#nextjs", "#developerlife"],
  loveCount: 128,
  commentCount: 12,
  repostCount: 3,
  shareCount: 9,
  visibility: "public",
  createdAt: "2025-08-01T08:00:00Z",
  updatedAt: "2025-08-01T08:30:00Z"
};

``

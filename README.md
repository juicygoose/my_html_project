erDiagram

    achievement {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        description text "not null"
        title text "not null"
        bucket_id uuid "not null"
        outdated_embeddings boolean "null"
        project_amount integer "null"
        building_owner text "null"
        embeddings vector "null"
    }

    achievement_deliverable {
        id uuid PK "not null"
        achievement_id uuid FK "not null"
        deliverable_id uuid FK "not null"
        achievement_id uuid "not null"
        deliverable_id uuid "not null"
    }

    achievement_package {
        id uuid PK "not null"
        achievement_id uuid FK "not null"
        package_id uuid FK "not null"
        achievement_id uuid "not null"
        package_id uuid "not null"
    }

    achievement_sector {
        id uuid PK "not null"
        achievement_id uuid FK "not null"
        sector_id uuid FK "not null"
        achievement_id uuid "not null"
        sector_id uuid "not null"
    }

    address {
        id integer PK "not null"
        freelance_id integer FK "not null"
        country_iso character "null"
        city character_varying "null"
        department character_varying "null"
        postal_code character_varying "null"
        region character_varying "null"
        street character_varying "null"
        street_number character_varying "null"
        full_address text "null"
    }

    application {
        id integer PK "not null"
        deal_id integer FK "null"
        freelance_id integer FK "null"
        referrer_id integer FK "null"
        next_available_revision_number integer "not null"
        status text "not null"
        referree_email character_varying "null"
        referree_phone character_varying "null"
        crm_activity_id integer "null"
        deal_id integer "null"
        freelance_id integer "null"
        tarification integer "null"
        fee_percentage numeric "null"
        motivation text "null"
        payment_terms text "null"
        refusal_reason text "null"
        creation_date timestamp_without_time_zone "null"
        last_update timestamp_without_time_zone "null"
        start_date timestamp_without_time_zone "null"
    }

    application_reporting {
        id integer PK "not null"
        application_id integer "not null"
        freelance_id integer "not null"
        new_status text "not null"
        timestamp timestamp_without_time_zone "not null"
        old_status text "null"
    }

    assistant_ratings {
        id integer PK "not null"
        is_relevant boolean "null"
        thread_id text "null"
    }

    availability {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        is_display boolean "not null"
        freelance_id integer "not null"
        is_available boolean "null"
        creation_timestamp timestamp_without_time_zone "null"
        last_update_timestamp timestamp_without_time_zone "null"
        next_available_date timestamp_without_time_zone "null"
    }

    client {
        id uuid PK "not null"
        client_organization_id uuid FK "not null"
        owner_freelance_id integer FK "null"
        user_id uuid FK "null"
        email text "not null"
        first_name text "not null"
        last_name text "not null"
        phone_number text "not null"
        source text "not null"
        is_internal boolean "null"
        position character_varying "null"
        crm_id integer "null"
        owner_freelance_id integer "null"
        notes text "null"
        created_at timestamp_with_time_zone "null"
        updated_at timestamp_with_time_zone "null"
    }

    client_organization {
        id uuid PK "not null"
        address_id integer FK "null"
        owner_freelance_id integer FK "null"
        name text "not null"
        is_internal boolean "null"
        vat_number character_varying "null"
        crm_id integer "null"
        owner_freelance_id integer "null"
        siret text "null"
        created_at timestamp_with_time_zone "null"
        updated_at timestamp_with_time_zone "null"
    }

    configs {
        id uuid PK "not null"
        name text "not null"
        config jsonb "null"
    }

    deal {
        id integer PK "not null"
        preferred_freelance_id integer FK "null"
        client_id uuid FK "null"
        notification_triggered boolean "not null"
        pipeline_id integer "not null"
        fee_percentage numeric "not null"
        payment_terms text "not null"
        uuid uuid "not null"
        business_trip_planned boolean "null"
        outdated_embeddings boolean "null"
        published boolean "null"
        owner_crm_name character_varying "null"
        postal_code character_varying "null"
        service_type character_varying "null"
        sizing character_varying "null"
        stage character_varying "null"
        status character_varying "null"
        work_rythm character_varying "null"
        workplace character_varying "null"
        contract_type contract_type "null"
        end_date date "null"
        publication_date date "null"
        start_date date "null"
        budget integer "null"
        crm_id integer "null"
        initial_deal_id integer "null"
        notification_count integer "null"
        organization_crm_id integer "null"
        owner_crm_id integer "null"
        project_duration integer "null"
        quantity integer "null"
        referral_freelance_id integer "null"
        retained_freelance_crm_id integer "null"
        city text "null"
        description text "null"
        name text "null"
        organization_name text "null"
        origin text "null"
        project_status text "null"
        supporting_documents_link text "null"
        creation_date timestamp_without_time_zone "null"
        last_update timestamp_without_time_zone "null"
        work_supplies varchar[] "null"
        embeddings vector "null"
    }

    deal_bookmark {
        id uuid PK "not null"
        deal_id integer FK "not null"
        freelance_id integer FK "not null"
        deal_id integer "not null"
        freelance_id integer "not null"
        created_at timestamp_with_time_zone "not null"
    }

    deal_phase {
        id uuid PK "not null"
        deal_id integer FK "not null"
        phase_id uuid FK "not null"
    }

    deal_profession {
        id uuid PK "not null"
        deal_id integer FK "not null"
        profession_id uuid FK "not null"
        deal_id integer "not null"
        profession_id uuid "not null"
        is_primary boolean "null"
    }

    deal_sector {
        id uuid PK "not null"
        deal_id integer FK "not null"
        sector_id uuid FK "not null"
        deal_id integer "not null"
        sector_id uuid "not null"
    }

    deal_specialty {
        id uuid PK "not null"
        deal_id integer FK "not null"
        specialty_id uuid FK "not null"
        deal_id integer "not null"
        specialty_id uuid "not null"
        is_primary boolean "null"
    }

    deletion_reason {
        freelance_id integer PK "not null"
        reason text "not null"
        timestamp timestamp_without_time_zone "not null"
    }

    deliverable {
        id uuid PK "not null"
        name text "not null"
        freelance_crm_id integer "null"
    }

    experience {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        end_date integer "not null"
        start_date integer "not null"
        description text "not null"
        title text "not null"
        type text "not null"
        outdated_embeddings boolean "null"
        location text "null"
        organization text "null"
        embeddings vector "null"
    }

    expertise {
        id uuid PK "not null"
        freelance_id integer FK "null"
        profession_id uuid FK "null"
        specialty_id uuid FK "null"
        index integer "not null"
        level expertise_level "null"
    }

    expertise_deliverable {
        id uuid PK "not null"
        deliverable_id uuid FK "not null"
        expertise_id uuid FK "not null"
    }

    expertise_package {
        id uuid PK "not null"
        expertise_id uuid FK "not null"
        package_id uuid FK "not null"
    }

    expertise_phase {
        id uuid PK "not null"
        expertise_id uuid FK "not null"
        phase_id uuid FK "not null"
    }

    external_ressources {
        id uuid PK "not null"
        call_to_action_link text "null"
        call_to_action_text text "null"
        description text "null"
        name text "null"
        picture_file_id text "null"
        promotion_description text "null"
        theme text "null"
        type text "null"
    }

    feedback {
        id uuid PK "not null"
        experience_id uuid FK "not null"
        display boolean "not null"
        date date "not null"
        email text "not null"
        first_name text "not null"
        last_name text "not null"
        phone text "not null"
        communication integer "null"
        deadlines_respect integer "null"
        deliverable_quality integer "null"
        details text "null"
    }

    file_owners {
        id integer PK "not null"
        file_id uuid FK "not null"
        user_id uuid FK "not null"
    }

    freelance {
        id integer PK "not null"
        legal_data_id integer FK "null"
        referral_id integer FK "null"
        user_id uuid FK "null"
        utm_id uuid FK "null"
        model boolean "not null"
        email character_varying "not null"
        first_name character_varying "not null"
        last_name character_varying "not null"
        phone character_varying "not null"
        rank integer "not null"
        linkedin_import_status text "not null"
        referral_code text "not null"
        version text "not null"
        uuid uuid "not null"
        crm_top_freelance boolean "null"
        get_acquainted boolean "null"
        has_legal_structure boolean "null"
        marketing_consent boolean "null"
        outdated_embeddings boolean "null"
        certifications bytea "null"
        education bytea[] "null"
        experiences bytea[] "null"
        acquisition_channel character_varying "null"
        city character_varying "null"
        country character_varying "null"
        duration character_varying "null"
        fulltime character_varying "null"
        linkedin_import_section character_varying "null"
        linkedin_url character_varying "null"
        mobility character_varying "null"
        profile_picture_bucket_key character_varying "null"
        remote_friendly character_varying "null"
        birth_date date "null"
        activity freelancer_activity_status "null"
        crm_labels int4[] "null"
        crm_id integer "null"
        tarification integer "null"
        banner_file_url text "null"
        crm_notes text "null"
        description text "null"
        headline text "null"
        occupation text "null"
        portfolio_bucket_key_list text "null"
        preferred_deal_size text "null"
        profile_pic_url text "null"
        summary text "null"
        last_preferences_update_time timestamp_without_time_zone "null"
        last_seen_opportunities timestamp_without_time_zone "null"
        registered_on timestamp_without_time_zone "null"
        profile_picture_file_id uuid "null"
        languages varchar[] "null"
        skills varchar[] "null"
        embeddings vector "null"
    }

    freelance_deal_rating {
        deal_id integer PK "not null"
        freelance_id integer PK "not null"
        is_relevant boolean "null"
    }

    freelance_language {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        language_id uuid FK "not null"
        level integer "not null"
    }

    freelance_legal_data {
        id integer PK "not null"
        freelance_id integer FK "null"
        isOnboarded boolean "not null"
        processing_status jsonb "not null"
        has_rc_pro_insurance boolean "null"
        has_ten_year_warranty_insurance boolean "null"
        wage_portage boolean "null"
        bic character_varying "null"
        billing_management_bucket_key character_varying "null"
        birth_city character_varying "null"
        birth_country character_varying "null"
        birth_country_iso character_varying "null"
        citizenship character_varying "null"
        citizenship_iso character_varying "null"
        factor_id character_varying "null"
        factor_management_bucket_key character_varying "null"
        first_name character_varying "null"
        headquarters_address_city character_varying "null"
        headquarters_address_country_iso character_varying "null"
        headquarters_address_department character_varying "null"
        headquarters_address_postal_code character_varying "null"
        headquarters_address_region character_varying "null"
        headquarters_address_street character_varying "null"
        headquarters_address_street_number character_varying "null"
        iban character_varying "null"
        identity_document_bucket_key character_varying "null"
        kbis_bucket_key character_varying "null"
        last_name character_varying "null"
        legal_forms_bucket_key character_varying "null"
        legal_person_type character_varying "null"
        legal_rep_address_city character_varying "null"
        legal_rep_address_country_iso character_varying "null"
        legal_rep_address_department character_varying "null"
        legal_rep_address_postal_code character_varying "null"
        legal_rep_address_region character_varying "null"
        legal_rep_address_street character_varying "null"
        legal_rep_address_street_number character_varying "null"
        legal_structure character_varying "null"
        mangopay_declaration_bucket_key character_varying "null"
        payment_provider_articles_of_association_doc_id character_varying "null"
        payment_provider_bank_account_id character_varying "null"
        payment_provider_identity_prood_doc_id character_varying "null"
        payment_provider_registration_proof_doc_id character_varying "null"
        payment_provider_shareholder_declaration_doc_id character_varying "null"
        payment_provider_ubo_declaration_doc_id character_varying "null"
        payment_provider_user_id character_varying "null"
        payment_provider_wallet_id character_varying "null"
        postal_code character_varying "null"
        rc_pro_bucket_key character_varying "null"
        rcs_registration_city character_varying "null"
        sirene_status_certificate_bucket_key character_varying "null"
        siret_number character_varying "null"
        social_capital character_varying "null"
        vat_intracommunity_number character_varying "null"
        vigilance_certificate_bucket_key character_varying "null"
        birth_date date "null"
        vat_percentage integer "null"
        business_name text "null"
        headquarters_address text "null"
        legal_rep_address text "null"
        creation_date timestamp_without_time_zone "null"
        last_update timestamp_without_time_zone "null"
    }

    freelance_preferences {
        freelance_id integer PK "not null"
        freelance_id integer FK "not null"
        is_application_processing_time_displayed boolean "not null"
        last_changed timestamp_with_time_zone "null"
    }

    geography_columns {
        coord_dimension integer "null"
        srid integer "null"
        f_geography_column name "null"
        f_table_catalog name "null"
        f_table_name name "null"
        f_table_schema name "null"
        type text "null"
    }

    geometry_columns {
        f_table_catalog character_varying "null"
        type character_varying "null"
        coord_dimension integer "null"
        srid integer "null"
        f_geometry_column name "null"
        f_table_name name "null"
        f_table_schema name "null"
    }

    kyc_document {
        id integer PK "not null"
        freelance_legal_data_id integer FK "null"
        document_type character_varying "null"
        factor_id character_varying "null"
        payment_provider_id character_varying "null"
        refusal_reason character_varying "null"
        status character_varying "null"
        refusal_origin kyc_refusal_origin "null"
        creation_date timestamp_without_time_zone "null"
        expiration_date timestamp_without_time_zone "null"
        legal_file_id uuid "null"
    }

    language {
        id uuid PK "not null"
        name text "not null"
    }

    opportunity_filter {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        phase_id uuid FK "null"
        profession_id uuid FK "null"
        specialty_id uuid FK "null"
        created_at timestamp_with_time_zone "not null"
        notify boolean "null"
        postal_codes int4[] "null"
        service_types service_type[] "null"
        package_id uuid "null"
        workplaces workplace[] "null"
    }

    opportunity_filter_phase {
        id uuid PK "not null"
        opportunity_filter_id uuid FK "not null"
        phase_id uuid FK "not null"
        opportunity_filter_id uuid "not null"
        phase_id uuid "not null"
    }

    opportunity_filter_profession {
        id uuid PK "not null"
        opportunity_filter_id uuid FK "not null"
        profession_id uuid FK "not null"
        opportunity_filter_id uuid "not null"
        profession_id uuid "not null"
    }

    opportunity_filter_specialty {
        id uuid PK "not null"
        opportunity_filter_id uuid FK "not null"
        specialty_id uuid FK "not null"
        opportunity_filter_id uuid "not null"
        specialty_id uuid "not null"
    }

    package {
        id uuid PK "not null"
        name text "not null"
        freelance_crm_id integer "null"
    }

    phase {
        id uuid PK "not null"
        name text "not null"
        deal_crm_id integer "null"
        freelance_crm_id integer "null"
    }

    postal_code_geography {
        id integer PK "not null"
        geo_point geography "not null"
        name text "not null"
        postal_code text "not null"
    }

    postal_code_radius {
        id integer PK "not null"
        freelance_id integer FK "null"
        opportunity_filter_id uuid FK "null"
        radius integer "not null"
        postal_code text "not null"
        city_name text "null"
    }

    profession {
        id uuid PK "not null"
        name text "not null"
        has_deliverable boolean "null"
        deal_crm_id integer "null"
        freelance_crm_id integer "null"
    }

    profession_specialty {
        id uuid PK "not null"
        profession_id uuid FK "not null"
        specialty_id uuid FK "not null"
    }

    project_deliverable {
        id uuid PK "not null"
        quotation_id integer FK "null"
        quotation_template_id integer FK "null"
        work_order_id uuid FK "null"
        option boolean "not null"
        unit text "not null"
        outdated_embeddings boolean "null"
        estimated_delivery_date date "null"
        index integer "null"
        revisions integer "null"
        quantity numeric "null"
        total_price numeric "null"
        unit_price numeric "null"
        description text "null"
        embeddings vector "null"
    }

    project_deliverable_with_fees {
        option boolean "null"
        estimated_delivery_date date "null"
        index integer "null"
        quotation_id integer "null"
        revisions integer "null"
        quantity numeric "null"
        total_amount_with_fees numeric "null"
        total_price numeric "null"
        unit_price numeric "null"
        unit_price_fees_only numeric "null"
        unit_price_with_fees numeric "null"
        description text "null"
        unit text "null"
        id uuid "null"
    }

    quotation {
        id integer PK "not null"
        application_id integer FK "null"
        freelance_id integer "not null"
        internal_id text "not null"
        revision_number integer "null"
        template_id integer "null"
        validity_duration integer "null"
        fee_percentage numeric "null"
        fee_total_specified numeric "null"
        comment text "null"
        description text "null"
        name text "null"
        payment_terms text "null"
        project_name text "null"
        quotation_url text "null"
        sender_comment text "null"
        status text "null"
        terms_and_conditions text "null"
        created_at timestamp_with_time_zone "null"
        updated_at timestamp_with_time_zone "null"
        client_quotation_pdf_file_id uuid "null"
        pdf_file_id uuid "null"
        recipient_id uuid "null"
    }

    quotation_template {
        id integer PK "not null"
        freelance_id integer FK "not null"
        description text "null"
        name text "null"
        created_at timestamp_with_time_zone "null"
        updated_at timestamp_with_time_zone "null"
    }

    quotation_with_amounts {
        application_id integer "null"
        freelance_id integer "null"
        id integer "null"
        revision_number integer "null"
        validity_duration integer "null"
        fee_amount numeric "null"
        fee_percentage numeric "null"
        fee_total_specified numeric "null"
        option_amount numeric "null"
        total_amount numeric "null"
        total_amount_without_fees numeric "null"
        description text "null"
        internal_id text "null"
        name text "null"
        payment_terms text "null"
        project_name text "null"
        quotation_url text "null"
        status text "null"
        terms_and_conditions text "null"
        created_at timestamp_with_time_zone "null"
        updated_at timestamp_with_time_zone "null"
        recipient_id uuid "null"
    }

    rank_reporting {
        id uuid PK "not null"
        freelance_id integer FK "null"
        timestamp timestamp_with_time_zone "not null"
        new_rank integer "null"
        old_rank integer "null"
    }

    referral {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        referred_freelance_id integer "not null"
        status referral_status "not null"
        creation_date date "null"
    }

    referral_freelance_ranking {
        count bigint "null"
        rank bigint "null"
        freelance_id integer "null"
    }

    sector {
        id uuid PK "not null"
        name text "not null"
        deal_crm_id integer "null"
        freelance_crm_id integer "null"
        icon_name text "null"
    }

    sector_freelance {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        sector_id uuid FK "not null"
        freelance_id integer "not null"
        sector_id uuid "not null"
    }

    sf_columns {
        team_member_id integer PK "not null"
        id uuid PK "not null"
        team_member_id integer FK "not null"
        team_member_id integer "not null"
        application_columns text[] "not null"
        deal_columns text[] "not null"
        freelance_columns text[] "not null"
        quotation_columns text[] "not null"
        software_columns text[] "not null"
        id uuid "not null"
    }

    sf_deal_assistant_reporting {
        id uuid PK "not null"
        crm_client_id integer "not null"
        created_at timestamp_with_time_zone "not null"
        crm_client_context text "null"
        crm_client_notes text "null"
        deal_notes text "null"
        linkedin_organization text "null"
        linkedin_profile text "null"
        llm_client_context text "null"
        llm_deal_description text "null"
        llm_profession_and_sector_filtering text "null"
    }

    skills {
        id integer PK "not null"
        skill character_varying "null"
        crm_id integer "null"
    }

    skills_deal {
        deal_id integer PK "not null"
        skill_id integer PK "not null"
        deal_id integer FK "not null"
        skill_id integer FK "not null"
    }

    skills_freelance {
        freelance_id integer PK "not null"
        skill_id integer PK "not null"
        freelance_id integer FK "not null"
        skill_id integer FK "not null"
    }

    software {
        id uuid PK "not null"
        name text "not null"
        freelance_crm_id integer "null"
        freelance_id integer "null"
        status software_status "null"
        refusal_reason text "null"
        picture_file_id uuid "null"
    }

    software_skill {
        id uuid PK "not null"
        freelance_id integer FK "not null"
        software_id uuid FK "not null"
        has_professional_licence boolean "not null"
        level integer "not null"
    }

    spatial_ref_sys {
        srid integer PK "not null"
        auth_name character_varying "null"
        proj4text character_varying "null"
        srtext character_varying "null"
        auth_srid integer "null"
    }

    specialty {
        id uuid PK "not null"
        name text "not null"
        deal_crm_id integer "null"
        freelance_crm_id integer "null"
    }

    specialty_deliverable {
        id uuid PK "not null"
        deliverable_id uuid FK "not null"
        specialty_id uuid FK "not null"
    }

    specialty_package {
        id uuid PK "not null"
        package_id uuid FK "not null"
        specialty_id uuid FK "not null"
    }

    specialty_per_profession {
        specialty_count bigint "null"
        profession_id uuid "null"
    }

    specialty_phase {
        id uuid PK "not null"
        phase_id uuid FK "not null"
        specialty_id uuid FK "not null"
    }

    support {
        id integer PK "not null"
        freelance_id integer FK "not null"
        category support_category "not null"
        message text "not null"
        creation_date timestamp_without_time_zone "not null"
        mission text "null"
        mission_url text "null"
        subject text "null"
    }

    team_members {
        id integer PK "not null"
        user_id uuid FK "null"
        is_assigned_inbound_deals boolean "not null"
        city character_varying "not null"
        body text "not null"
        email text "not null"
        name text "not null"
        phone text "not null"
        profile_picture_url text "not null"
        crm_id integer "null"
        team text "null"
    }

    utm {
        id uuid PK "not null"
        name text "not null"
    }

    work_order {
        id uuid PK "not null"
        deal_id integer FK "not null"
        sales_date date "not null"
        start_date date "not null"
        contract_type text "not null"
        end_date date "null"
        created_at timestamp_with_time_zone "null"
    }

    achievement ||--o{ achievement_deliverable : "achievement_deliverable(achievement_id) -> achievement(id)"
    achievement ||--o{ achievement_package : "achievement_package(achievement_id) -> achievement(id)"
    achievement ||--o{ achievement_sector : "achievement_sector(achievement_id) -> achievement(id)"
    address ||--o{ client_organization : "client_organization(address_id) -> address(id)"
    application ||--o{ quotation : "quotation(application_id) -> application(id)"
    client ||--o{ deal : "deal(client_id) -> client(id)"
    client_organization ||--o{ client : "client(client_organization_id) -> client_organization(id)"
    deal ||--o{ application : "application(deal_id) -> deal(id)"
    deal ||--o{ deal_bookmark : "deal_bookmark(deal_id) -> deal(id)"
    deal ||--o{ deal_phase : "deal_phase(deal_id) -> deal(id)"
    deal ||--o{ deal_profession : "deal_profession(deal_id) -> deal(id)"
    deal ||--o{ deal_sector : "deal_sector(deal_id) -> deal(id)"
    deal ||--o{ deal_specialty : "deal_specialty(deal_id) -> deal(id)"
    deal ||--o{ skills_deal : "skills_deal(skill_id) -> deal(id)"
    deal ||--o{ work_order : "work_order(deal_id) -> deal(id)"
    deliverable ||--o{ achievement_deliverable : "achievement_deliverable(deliverable_id) -> deliverable(id)"
    deliverable ||--o{ expertise_deliverable : "expertise_deliverable(deliverable_id) -> deliverable(id)"
    deliverable ||--o{ specialty_deliverable : "specialty_deliverable(deliverable_id) -> deliverable(id)"
    experience ||--o{ feedback : "feedback(experience_id) -> experience(id)"
    expertise ||--o{ expertise_deliverable : "expertise_deliverable(expertise_id) -> expertise(id)"
    expertise ||--o{ expertise_package : "expertise_package(expertise_id) -> expertise(id)"
    expertise ||--o{ expertise_phase : "expertise_phase(expertise_id) -> expertise(id)"
    files ||--o{ file_owners : "file_owners(file_id) -> files(id)"
    freelance ||--o{ achievement : "achievement(freelance_id) -> freelance(id)"
    freelance ||--o{ address : "address(freelance_id) -> freelance(id)"
    freelance ||--o{ application : "application(freelance_id) -> freelance(id)"
    freelance ||--o{ application : "application(referrer_id) -> freelance(id)"
    freelance ||--o{ availability : "availability(freelance_id) -> freelance(id)"
    freelance ||--o{ client : "client(owner_freelance_id) -> freelance(id)"
    freelance ||--o{ client_organization : "client_organization(owner_freelance_id) -> freelance(id)"
    freelance ||--o{ deal : "deal(preferred_freelance_id) -> freelance(id)"
    freelance ||--o{ deal_bookmark : "deal_bookmark(freelance_id) -> freelance(id)"
    freelance ||--o{ experience : "experience(freelance_id) -> freelance(id)"
    freelance ||--o{ expertise : "expertise(freelance_id) -> freelance(id)"
    freelance ||--o{ freelance : "freelance(referral_id) -> freelance(id)"
    freelance ||--o{ freelance_language : "freelance_language(freelance_id) -> freelance(id)"
    freelance ||--o{ freelance_legal_data : "freelance_legal_data(freelance_id) -> freelance(id)"
    freelance ||--o{ freelance_preferences : "freelance_preferences(freelance_id) -> freelance(id)"
    freelance ||--o{ opportunity_filter : "opportunity_filter(freelance_id) -> freelance(id)"
    freelance ||--o{ postal_code_radius : "postal_code_radius(freelance_id) -> freelance(id)"
    freelance ||--o{ quotation_template : "quotation_template(freelance_id) -> freelance(id)"
    freelance ||--o{ rank_reporting : "rank_reporting(freelance_id) -> freelance(id)"
    freelance ||--o{ referral : "referral(freelance_id) -> freelance(id)"
    freelance ||--o{ sector_freelance : "sector_freelance(freelance_id) -> freelance(id)"
    freelance ||--o{ skills_freelance : "skills_freelance(freelance_id) -> freelance(id)"
    freelance ||--o{ software_skill : "software_skill(freelance_id) -> freelance(id)"
    freelance ||--o{ support : "support(freelance_id) -> freelance(id)"
    freelance_legal_data ||--o{ freelance : "freelance(legal_data_id) -> freelance_legal_data(id)"
    freelance_legal_data ||--o{ kyc_document : "kyc_document(freelance_legal_data_id) -> freelance_legal_data(id)"
    language ||--o{ freelance_language : "freelance_language(language_id) -> language(id)"
    opportunity_filter ||--o{ opportunity_filter_phase : "opportunity_filter_phase(opportunity_filter_id) -> opportunity_filter(id)"
    opportunity_filter ||--o{ opportunity_filter_profession : "opportunity_filter_profession(opportunity_filter_id) -> opportunity_filter(id)"
    opportunity_filter ||--o{ opportunity_filter_specialty : "opportunity_filter_specialty(opportunity_filter_id) -> opportunity_filter(id)"
    opportunity_filter ||--o{ postal_code_radius : "postal_code_radius(opportunity_filter_id) -> opportunity_filter(id)"
    package ||--o{ achievement_package : "achievement_package(package_id) -> package(id)"
    package ||--o{ expertise_package : "expertise_package(package_id) -> package(id)"
    package ||--o{ specialty_package : "specialty_package(package_id) -> package(id)"
    phase ||--o{ deal_phase : "deal_phase(phase_id) -> phase(id)"
    phase ||--o{ expertise_phase : "expertise_phase(phase_id) -> phase(id)"
    phase ||--o{ opportunity_filter : "opportunity_filter(phase_id) -> phase(id)"
    phase ||--o{ opportunity_filter_phase : "opportunity_filter_phase(phase_id) -> phase(id)"
    phase ||--o{ specialty_phase : "specialty_phase(phase_id) -> phase(id)"
    profession ||--o{ deal_profession : "deal_profession(profession_id) -> profession(id)"
    profession ||--o{ expertise : "expertise(profession_id) -> profession(id)"
    profession ||--o{ opportunity_filter : "opportunity_filter(profession_id) -> profession(id)"
    profession ||--o{ opportunity_filter_profession : "opportunity_filter_profession(profession_id) -> profession(id)"
    profession ||--o{ profession_specialty : "profession_specialty(profession_id) -> profession(id)"
    quotation ||--o{ project_deliverable : "project_deliverable(quotation_id) -> quotation(id)"
    quotation_template ||--o{ project_deliverable : "project_deliverable(quotation_template_id) -> quotation_template(id)"
    sector ||--o{ achievement_sector : "achievement_sector(sector_id) -> sector(id)"
    sector ||--o{ deal_sector : "deal_sector(sector_id) -> sector(id)"
    sector ||--o{ sector_freelance : "sector_freelance(sector_id) -> sector(id)"
    skills ||--o{ skills_deal : "skills_deal(deal_id) -> skills(id)"
    skills ||--o{ skills_freelance : "skills_freelance(skill_id) -> skills(id)"
    software ||--o{ software_skill : "software_skill(software_id) -> software(id)"
    specialty ||--o{ deal_specialty : "deal_specialty(specialty_id) -> specialty(id)"
    specialty ||--o{ expertise : "expertise(specialty_id) -> specialty(id)"
    specialty ||--o{ opportunity_filter : "opportunity_filter(specialty_id) -> specialty(id)"
    specialty ||--o{ opportunity_filter_specialty : "opportunity_filter_specialty(specialty_id) -> specialty(id)"
    specialty ||--o{ profession_specialty : "profession_specialty(specialty_id) -> specialty(id)"
    specialty ||--o{ specialty_deliverable : "specialty_deliverable(specialty_id) -> specialty(id)"
    specialty ||--o{ specialty_package : "specialty_package(specialty_id) -> specialty(id)"
    specialty ||--o{ specialty_phase : "specialty_phase(specialty_id) -> specialty(id)"
    team_members ||--o{ sf_columns : "sf_columns(team_member_id) -> team_members(id)"
    users ||--o{ client : "client(user_id) -> users(id)"
    users ||--o{ file_owners : "file_owners(user_id) -> users(id)"
    users ||--o{ freelance : "freelance(user_id) -> users(id)"
    users ||--o{ team_members : "team_members(user_id) -> users(id)"
    utm ||--o{ freelance : "freelance(utm_id) -> utm(id)"
    work_order ||--o{ project_deliverable : "project_deliverable(work_order_id) -> work_order(id)"

(function () {

    // Admin has full access
    if (gs.hasRole('admin')) {
        answer = true;
        return;
    }

    // EEE users can access EEE records
    if (gs.hasRole('bb1') && current.branch == 'EEE') {
        answer = true;
        return;
    }

    // Users with bb2 can create records
    if (gs.hasRole('bb2')) {
        answer = true;
        return;
    }

    // Users with bb3 can edit EEE records
    if (gs.hasRole('bb3') && current.branch == 'EEE') {
        answer = true;
        return;
    }

    // Users with bb4 can delete EEE records
    if (gs.hasRole('bb4') && current.branch == 'EEE') {
        answer = true;
        return;
    }

    // Deny access
    answer = false;

})();
